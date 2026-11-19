<%*
const kanbanPath = "Kanban.md";

const statuses = {
	"To Do": [],
	"In Progress": [],
	"Awaiting 3rd Party": [],
	"Done": [],
};

const skipFiles = new Set([
	kanbanPath,
	"Dashboard.md",
]);

const files = app.vault.getMarkdownFiles();

for (const file of files) {
	if (skipFiles.has(file.path)) continue;
	if (file.path.startsWith("Back End/")) continue;

	const content = await app.vault.read(file);
	const lines = content.split("\n");

	for (const line of lines) {
		const trimmed = line.trim();

		if (!trimmed.startsWith("- [")) continue;

		const isDone =
			trimmed.startsWith("- [x]") ||
			trimmed.startsWith("- [X]");

		const taskText = trimmed
			.replace(/^- \[[ xX]\]\s*/, "")
			.trim();

		if (!taskText) continue;

		const sourceLink = `[[${file.path.replace(/\.md$/, "")}]]`;
		const taskLine = `- [${isDone ? "x" : " "}] ${taskText} ${sourceLink}`;

		if (isDone) {
			statuses["Done"].push(taskLine);
		} else if (/in progress/i.test(taskText)) {
			statuses["In Progress"].push(taskLine);
		} else if (/awaiting|waiting|blocked|third party|3rd party/i.test(taskText)) {
			statuses["Awaiting 3rd Party"].push(taskLine);
		} else {
			statuses["To Do"].push(taskLine);
		}
	}
}

const output = `## To Do

${statuses["To Do"].join("\n")}

## In Progress

${statuses["In Progress"].join("\n")}

## Awaiting 3rd Party

${statuses["Awaiting 3rd Party"].join("\n")}

## Done

${statuses["Done"].join("\n")}

%% kanban:settings
\`\`\`
{"kanban-plugin":"board","list-collapse":[false,false,false,false]}
\`\`\`
%%`;

const kanbanFile = app.vault.getAbstractFileByPath(kanbanPath);

if (!kanbanFile) {
	await app.vault.create(kanbanPath, output);
} else {
	await app.vault.modify(kanbanFile, output);
}

new Notice("✅ Kanban synced from all vault tasks");

tR = "";
%>