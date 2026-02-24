
<%*
const file = app.workspace.getActiveFile();
const content = await app.vault.read(file);
const lines = content.split('\n');

const headingRegex = /^(#{1,6})\s+(.+)$/;
const headings = [];

for (const line of lines) {
  const match = line.match(headingRegex);
  if (match) {
    const level = match[1].length;
    const text = match[2].trim();
    if (text === "Table of Contents") continue;
    headings.push({ level, text });
  }
}

if (headings.length === 0) {
  tR += "_No headings found._";
} else {
  const minLevel = Math.min(...headings.map(h => h.level));
  const tocLines = [];

  for (const heading of headings) {
    const indent = "    ".repeat(heading.level - minLevel);
    tocLines.push(`${indent}1. ${heading.text}`);
  }

  tR += tocLines.join('\n');
}
%>
