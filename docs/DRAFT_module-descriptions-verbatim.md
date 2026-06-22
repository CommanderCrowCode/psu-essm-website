# DRAFT — True-verbatim module descriptions (English) vs TQF2 Appendix ฉ

**STATUS: DRAFT — NOT PUBLISHED.** Reference for a possible future upgrade of the
`/curriculum/` "Module descriptions" section from the current **as-published-cleaned**
text to **true char-for-char verbatim** English, should the operator request it.

**Source:** `/home/tanwa/academics/aunqa/program_spec/tqf2.md`, Appendix ฉ
(ภาคผนวก ฉ — "คำอธิบายรายวิชา/ชุดวิชาตามแนวทาง OBE"), the English columns of the
OBE course-description table (~lines 3219–3520).

**Method:** The source table is a broken ASCII grid in which each English cell is
wrapped across many rows, frequently splitting words mid-token (e.g. "ap proaches",
"envir onmental", "te chnology"). Below, each cell is reconstructed by concatenating
its fragments **in source order** and rejoining ONLY the table-wrapping splits. No word
is added, removed, reordered, or re-spelled. Source quirks are **preserved verbatim**
(singular/plural as written, missing articles, the redundant "Able to", the noun-phrase
ELO, "information Up-to-date", and missing trailing periods). The markdown numbering
artifact `1\.` in the source renders as `1.`.

> ⚠️ Because the source physically line-wraps mid-word, "char-for-char" here means
> char-for-char of the **author's intended cell text** (wrapping splits removed). It is
> not a byte-copy of the wrapped grid. This is the strongest verbatim claim the source
> medium supports; flagged honestly per the zero-invented-facts rule.

---

## 979-701 Advanced Research Methodology · 3((2)-2-5) · required, non-credit

**Description (verbatim):**
> Advanced methods and approaches in selecting research topic and tools in environmental science, technology and management; information search for literature review or previous research, experimental and research design, preparation and presentation for proposal, collecting and analysis of data; research quality and ethics in research; report writing and presentation

**Course learning outcomes (verbatim):**
> Students are able to
> 1. Disseminate information, news and academic articles in the field of environmental technology.
> 2. Apply research processes and techniques related to technology and solutions to environmental problems appropriately and effectively.
> 3. Develop and disseminate up-to-date and reliable knowledge in the fields of technology and environmental management.

---

## 979-702 Advanced Environmental Data Analytics · 1((1)-0-2) · required, non-credit

**Description (verbatim):**
> Principles of information; advanced technologies for collecting data, storing, accessing, displaying, analyzing data; the use of advanced statistical and mathematical tools to analyze environmental data in various fields; advanced environmental modeling; machine learning; geographic information system; decision support system; creating reports and using the results to guide environmental management planning

**Course learning outcomes (verbatim):**
> Students are able to
> 1. Analyze environmental data sets to identify patterns and trends, demonstrating proficiency in data mining and statistical techniques.
> 2. Evaluate the impact of human activities on the environment by applying advanced modeling and simulation methods, showcasing critical thinking and problem-solving skills.
> 3. Synthesize and communicate complex environmental data and analysis results effectively to diverse stakeholders, demonstrating advanced communication and presentation abilities.

---

## 979-703 Seminar · 1((1)-0-2) · required, non-credit

**Description (verbatim):**
> Environmental literature review for presentation; discussion under supervision of experts; presentation of research proposal and progress; applications of multimedia technology in communication of scientific data for enhancing public awareness and understanding

**Course learning outcomes (verbatim):**
> Students are able to
> 1. Discuss the selected environmental scientific research
> 2. Apply multimedia technology for communication of scientific data
> 3. Apply the concept of the environmental research for thesis work

*(Source omits trailing periods on these three ELOs.)*

---

## 979-801 Thesis · 48(0-144-0) · Plan 1.1   &   979-802 Thesis · 72(0-216-0) · Plan 1.2

*(Source rows for 979-801 and 979-802 carry identical English description and ELO text.)*

**Description (verbatim):**
> Study, design and development of the research topics related to science, technology and environmental management under the guidance of the thesis advisor committees; developing the research to create innovation or new knowledge in environmental fields

**Course learning outcomes (verbatim):**
> Students are able to
> 1. Analyze knowledge principles in the fields of technology and environmental management correctly.
> 2. Able to disseminate information, news and academic articles in the field of modern environmental technology.
> 3. Appropriate and effective application of research processes and techniques related to technology and solutions to environmental problems.
> 4. Systematically discuss the relationship between knowledge in the field of technology and environmental management and knowledge in other related fields.
> 5. Develop and disseminate information Up-to-date and reliable knowledge in the fields of technology and environmental management.

---

## Deltas — verbatim (above) vs currently PUBLISHED "as-cleaned" (live `/curriculum/`)

The published version made small readability cleanups. To upgrade to true-verbatim,
revert each of these:

| Course | Field | Published (as-cleaned) | Verbatim (source) |
|---|---|---|---|
| 979-701 | desc | "research topic**s**" | "research topic" (singular) |
| 979-701 | desc | "preparation and presentation **of the** proposal" | "preparation and presentation **for** proposal" |
| 979-702 | desc | "collecting, storing, accessing, displaying **and** analyzing data" | "collecting **data**, storing, accessing, displaying, analyzing data" |
| 979-702 | desc | "geographic information system**s**" / "decision support system**s**" | "geographic information system" / "decision support system" (singular) |
| 979-703 | desc | "under **the** supervision" / "in **the** communication" | "under supervision" / "in communication" (no article) |
| 979-703 | ELO3 | "concept of environmental research **to** thesis work" | "concept of **the** environmental research **for** thesis work" |
| 979-703 | ELOs | trailing periods added | source has **no** trailing periods |
| 979-801/802 | desc | "the **thesis-advisory committee**" | "the **thesis advisor committees**" |
| 979-801/802 | desc | "of **the** research topics" → kept as "research topics" | source: "of **the** research topics" |
| 979-801/802 | ELO2 | "Disseminate …" (dropped redundant "Able to") | "**Able to** disseminate …" |
| 979-801/802 | ELO3 | reworded to imperative "Apply …" | noun phrase "**Appropriate and effective application of** …" |
| 979-801/802 | ELO5 | "up-to-date and reliable knowledge" | "information **Up-to-date** and reliable knowledge" |

**Recommendation:** Keep the published as-cleaned text for readability for v1 (it reads
as professional English and preserves all facts). Hold this verbatim draft in reserve;
switch only if the operator/QA explicitly wants the exact TQF2 English reproduced,
quirks and all. Either way, the **Thai** column is the ultimate canonical text; this
draft concerns the TQF2's own **English** column only.
