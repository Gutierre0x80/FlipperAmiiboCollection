# FlipperAmiiboVault

A cleaned and organized collection of **900+ Amiibo NFC files for Flipper Zero**, covering nearly the entire Nintendo Switch-era Amiibo catalog.

The files are already in `.nfc` format and organized by game/series, so you can copy them to your Flipper and use them directly.

## How to use

Copy the `Amiibo` folder to:

```text
SD:/nfc/
```

Then open:

```text
NFC → Saved → Amiibo
```

Pick the Amiibo you want and press **Emulate**.

Tested with **Flipper Zero + Nintendo Switch 2**, including Animal Crossing: New Horizons.

## Why publish another Amiibo repository?

There are already a lot of Amiibo collections online, but while testing them I found that several files were technically readable by the Flipper Zero and still rejected by Nintendo games.

For example, Animal Crossing would detect the NFC scan but return:

```text
That's not an amiibo.
Please use an Animal Crossing character's amiibo.
```

The problem was not the NFC emulation itself. Some dumps had incomplete or inconsistent NTAG215 data.

Common issues included:

```text
Page 133: 00 00 00 00
Page 134: 00 00 00 00
```

and, in some cases, an incorrect `UID:` in the Flipper NFC header.

The files in this repository were cleaned and normalized so that:

- NTAG215 PWD is rebuilt correctly
- PACK is set correctly
- the Flipper UID header matches the tag data
- duplicate Amiibo dumps are removed
- meaningful variants are kept
- folders are organized by game and series

The fix was tested in practice with Animal Crossing Sanrio Amiibo that were previously rejected and worked correctly after repair.

## Collection

The repository includes Amiibo from:

- Animal Crossing
- Super Smash Bros.
- Super Mario
- The Legend of Zelda
- Splatoon
- Monster Hunter
- Metroid
- Fire Emblem
- Kirby
- Mario Sports Superstars
- PowerUpBands
- Yu-Gi-Oh!
- and more

Animal Crossing alone includes Series 1–5, Welcome Amiibo, Sanrio, figures, promos and additional variants.

## Notes

This collection is deduplicated by the Amiibo data itself, not just by filename. Different dumps of the same Amiibo can have different UIDs, so comparing filenames or file hashes alone is not enough.

Saved-data variants that actually change functionality were kept separately instead of being removed as duplicates.

This project is not affiliated with Nintendo or Flipper Devices.

Use Amiibo backups only where you have the appropriate rights and permissions.
