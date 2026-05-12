# OpenSpeaks Tome

OpenSpeaks Tome is a browser-based tool for creating and editing metadata for audio, video, image, and document files. It helps you prepare Wikimedia Commons file pages, keep metadata in a reusable JSON format, and import or edit records from archive formats used by language documentation projects.

It is made for people who work with language documentation, oral history, and community archives.

## What this tool does

You can use this tool to:

- Fill in metadata for a media file in a form.
- Generate Wikimedia Commons wikitext for a file page.
- Create or edit OpenSpeaks JSON.
- Import metadata from a Commons file page pasted as text.
- Import metadata from Lameta / OPEX files.
- Import metadata from BLAM / CMDI files.
- Add oral history documentation fields.
- Add subtitle and transcription details.
- Copy or download the generated output.

The tool runs in the browser. It does not need a server.

## Who this is for

This tool is for:

- Language archivists.
- Community researchers.
- Oral history teams.
- Documentation assistants.
- Wikimedians working on Commons uploads.
- Editors who prepare files for archive deposit.

If you are not a developer, you can still use it. You only need to fill in the form and copy the output.

## Main outputs

The tool can generate:

- Wikimedia Commons wikitext.
- OpenSpeaks JSON.
- Markdown.
- HTML.

Planned outputs and import support include:

- Lameta / OPEX export.
- BLAM / CMDI export.
- CSV and spreadsheet-based editing.

## What metadata it can hold

The form covers these kinds of information:

- File name.
- File type.
- Title and original title.
- Description.
- Project name.
- Language.
- Dialect.
- Location.
- Date.
- Runtime.
- Colour and sound.
- Producer, director, writer, cinematographer, editor, and recordist.
- Cast and interviewee names.
- Gender, birth year, birth place, and Wikidata QID.
- Genre and topic.
- Subtitle language and subtitle credits.
- Oral history consent and review details.
- Source, author, license, and categories.
- Identifiers such as DOI, EIDR, IMDb, and ISRC.

## How to use it

### 1. Open the tool

Open the web page in your browser.

### 2. Fill in the form

Enter the file details in the tabs.

Suggested order:

- Basic Info.
- Production.
- People.
- Subtitles and Oral History.
- License.
- Preview and Export.

### 3. Add people details

For interviewees or speakers, fill in:

- Full name.
- Wikidata QID, if known.
- Gender.
- Speaker role.

If the QID is known, the tool can link the person properly in the wiki output.

### 4. Add subtitles or transcript details

If the file has subtitles:

- Enter the subtitle language.
- Enter the TimedText page or URL.
- Enter the names of the subtitle creators.
- Enter the names of the subtitle editors or reviewers.

If a slash is used in the editor/reviewer field, the tool can separate editors and reviewers.

Example:

- `Name1, Name2 / Name3, Name4`

This can become:

- `Name1 (editor), Name2 (editor); Name3 (reviewer), Name4 (reviewer)`

### 5. Add oral history details

If the file is part of oral history documentation, fill in:

- Recording context.
- Equipment.
- Interviewer.
- Recorder.
- Consent type.
- Consent informed.
- Consent revocable.
- Sensitive content.
- Community review.
- Transcript details.

The tool uses these fields to build the OpenSpeaks Oral History Documentation Record.

### 6. Preview the result

Use the preview area to check the generated text before copying it.

This is important because it lets you see:

- Commons wikitext.
- The OpenSpeaks template.
- Author and moral rights lines.
- Subtitles formatting.
- Categories.
- Oral history documentation tables.

### 7. Copy or download

After checking the result, you can:

- Copy the text.
- Download the output.
- Save the JSON for later editing.

## Import options

### OpenSpeaks JSON

Use this when you already have a JSON file exported from the tool.

The tool will repopulate the form with the saved values.

### Commons wikitext

Use this when you already have a file page text from Wikimedia Commons.

Paste the wikitext into the import box, then parse it into the form.

### Lameta / OPEX

Use this for files prepared in Endangered Languages Archive workflows.

The tool can read OPEX and IMDI-based metadata and map the values into the form.

### BLAM / CMDI

Use this for metadata from Language Archive Cologne workflows.

The tool can read BLAM-related metadata and map it into the form.

## Export options

### Wikimedia Commons wikitext

This is the main output for Commons uploads.

It includes:

- `{{Information}}`
- `{{OpenSpeaks}}` or `{{OpenSpeaks image}}`
- subtitle information
- oral history documentation
- license
- categories

### OpenSpeaks JSON

This is the internal editable record.

It is useful when:

- you want to save work and return later,
- you want to share metadata with another editor,
- you want to import the same record again.

### Markdown and HTML

These are useful for:

- internal documentation,
- sharing metadata outside Commons,
- reports,
- draft records.

## Author and rights handling

The tool separates two ideas:

- Moral rights.
- Copyright.

When interviewees are present, the author line can show their names or Wikidata links.

When a Wikimedia username is available, the tool can use:

- `[[User:Username]]`

If no username is available, it can use the copyright holder text instead.

The tool no longer needs a separate `Copyright_holder` parameter in the OpenSpeaks template output.

## How subtitles are formatted

The subtitle line is built from:

- Subtitle language.
- TimedText page or URL.
- Subtitle creators.
- Subtitle editors or reviewers.

Example output:

- `In [[TimedText:...|Nepali]] by Name1, Name2; Name3 (editor), Name4 (reviewer)`

If no slash is used in the editor/reviewer field, the tool applies a simple default rule.

## OpenSpeaks Oral History Documentation Record

The tool includes a structured documentation block for oral history files.

It is divided into three parts:

### Parameter 1: Provenance and consent

Includes:

- Language.
- Dialect.
- Topic.
- Recording location.
- Recording date.
- Recording context.
- Equipment.
- Project name.
- Speakers.
- Speaker roles.
- Interviewer.
- Recorder.
- Consent type.
- Consent informed.
- Consent revocable.
- Sensitive content.
- Consent record location.

### Parameter 2: Community review

Includes:

- Community reviewed.
- Review date.
- Reviewers.
- Review notes.

### Parameter 3: Multilingual transcription and subtitles

Includes:

- Subtitles available.
- Subtitle details.
- Transcript available.
- Transcript details.
- Transcript language(s).

## Files and formats supported

Supported now:

- OpenSpeaks JSON.
- Wikimedia Commons wikitext.
- HTML.
- Markdown.

Supported for import or planned export:

- Lameta / OPEX.
- BLAM / CMDI.
- CSV.
- Excel.

## Versioning

The tool uses a schema version in the saved JSON.
The app version can be shown separately in the footer or documentation page.

Example:

- App version: `0.1.0-alpha`
- Schema version: `1.2`

## Running locally

You can run the tool locally by opening the HTML version in a browser or by using the React app in a local development setup.

If you use the React app:

- Open the project in your editor.
- Run the app locally.
- Test the form, import, and export functions before publishing.

If you use the HTML version:

- Open the file directly in the browser.
- Check the browser console if the page does not show.

## Publishing on GitHub Pages

This tool can be published as a static site on GitHub Pages.

Basic steps:

- Put the project in a GitHub repository.
- Add the built static files or a single `index.html`.
- Enable GitHub Pages in the repository settings.
- Share the Pages URL with testers.

If the project is a React app, it usually needs a build step before publishing.

If the project is a single HTML file, it can be uploaded directly.

## For developers

### Data model

The app uses one internal metadata record as the source of truth.

That record holds:

- file details,
- people details,
- oral history details,
- subtitle details,
- rights details,
- export data.

### Importers and exporters

The code should keep import and export logic separate from the form UI.

Useful modules:

- JSON importer/exporter.
- Commons wikitext parser.
- OPEX / IMDI importer/exporter.
- BLAM / CMDI importer/exporter.
- Subtitle formatter.
- Author line formatter.

### Future work

Planned additions:

- CSV export and import.
- Excel export and import.
- Better mapping from archive formats into the OpenSpeaks schema.
- A documentation page inside the deployed tool.

## Documentation in the deployed tool

Yes, the README can also be shown as a documentation page in the deployed tool.

A simple way to do this is:

- Keep README.md in the GitHub repo.
- Add a “Documentation” or “Help” tab in the app.
- Load the Markdown content and display it as a read-only page.
- Or keep a separate documentation page in HTML and link to it from the tool.

If you want the documentation to be available directly on GitHub Pages, the tool can link to a `/docs` page or a `README` view rendered in HTML.

## License

This project is under the MIT License.

## Project link

Current prototype: [OpenSpeaks Tome]([https://psubhashish.github.io/metadata-generator/](https://openspeaks.github.io/metadata-generator/))
