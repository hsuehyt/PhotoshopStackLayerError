# Photoshop Stack Layer Error

Troubleshooting Photoshop **Load Files into Stack** Error 44 (`Cannot convert`) involving `StackSupport.jsx` on Windows.

## Symptoms

Running **File > Scripts > Load Files into Stack...** fails with Error 44 while evaluating a support script.

## Proposed cause

The supplied troubleshooting notes attribute the error to non-ASCII characters in a script without a UTF-8 byte order mark (BOM), interpreted using a local Windows character encoding. This explanation has not been independently verified.

## Workaround: save as UTF-8 with BOM

1. Close Photoshop completely.
2. Locate `StackSupport.jsx` in your Photoshop installation, typically:

   ```text
   C:\Program Files\Adobe\Adobe Photoshop 2026\Presets\Scripts\Stack Scripts Only\StackSupport.jsx
   ```

3. Make a backup of the original file.
4. Open the script in an editor and save it as **UTF-8 with BOM**. Keep the `.jsx` extension.
5. If saving inside `Program Files` requires administrator permission, edit a copy and replace the installed file afterward.
6. Restart Photoshop and retry **Load Files into Stack**.

Adjust the installation path for your Photoshop version. If the workaround causes problems, restore the backup.

## Alternative described in the notes

Replace non-ASCII em dashes (`—`) in script comments with ASCII hyphens (`-`), then save and restart Photoshop. Back up the script before editing.

## Project files

The local project includes `StackSupport.jsx`, troubleshooting notes, and an error screenshot. Those files have not yet been uploaded to this repository.

## Attribution

`StackSupport.jsx` contains Adobe copyright notices. This project is an independent troubleshooting resource and is not affiliated with Adobe. No license to Adobe code is granted here.
