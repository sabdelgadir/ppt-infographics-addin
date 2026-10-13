# Infographics Library — PowerPoint add-in

A ribbon button for PowerPoint that opens a gallery of ready-made infographics. Click one and it is added as a new, fully editable slide.

## Install (Mac)

1. Download `manifest.xml` from this repository.
2. In Finder, press **Cmd + Shift + G** and go to:
   `~/Library/Containers/com.microsoft.Powerpoint/Data/Documents/wef`
   (create the `wef` folder if it isn't there).
3. Copy `manifest.xml` into that folder.
4. Quit PowerPoint completely and open it again.
5. Open any presentation. You'll see an **Infographics** tab next to **Insert**.
   If you don't, go to **Home → Add-ins** (or **Insert → Add-ins → My Add-ins**) and pick **Infographics Library** under *Developer Add-ins*.

## Install (Windows)

1. Put `manifest.xml` in a shared network folder.
2. PowerPoint → **File → Options → Trust Center → Trust Center Settings → Trusted Add-in Catalogs**. Add the folder path, tick **Show in Menu**, restart PowerPoint.
3. **Insert → My Add-ins → Shared Folder** → **Infographics Library**.

For the whole team, an M365 admin can deploy `manifest.xml` from **Admin Center → Settings → Integrated apps**.

## Add a new design

1. Make the infographic on a single slide in PowerPoint (16:9). Save it as its own `.pptx`.
2. Export that slide as a PNG thumbnail (**File → Export → PNG**).
3. Upload both into the `designs` folder here.
4. Open `designs.json` and add an entry (copy an existing one and change the names):

```json
{
  "name": "My New Design",
  "category": "Process",
  "file": "designs/my-new-design.pptx",
  "thumbnail": "designs/my-new-design.png"
}
```

Remember the comma between entries. GitHub publishes the change within a minute or two; close and reopen the panel to see it.

## Files

| File | What it is |
|---|---|
| `manifest.xml` | Tells PowerPoint where the add-in lives and adds the ribbon button |
| `taskpane.html` | The gallery panel |
| `designs.json` | The list of designs shown in the gallery |
| `designs/` | One `.pptx` and one `.png` per design |
| `assets/` | Ribbon icons |
| `commands.html` | Required by PowerPoint; nothing to edit |

Note: this repository is public, so anything in `designs/` can be downloaded by anyone. Keep company or purchased artwork out of it.
