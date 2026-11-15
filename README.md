# Five Nights at Freddy's: Killer in Purple — Reverse Engineering Notes

Fan game by Goldie Entertainment. Original: https://gamejolt.com/games/KillerInPurple/507258

## Technical details
- Engine: Unreal Engine 4.27 (`++UE4+Release-4.27`)
- Pak: `KillerInPurple-WindowsNoEditor.pak`, version V11 (Fnv64BugFix)
- Encryption: AES-256, encrypted file data (index unencrypted)
- Compression: Oodle, Zlib

## AES key
`0x741EE93575B56A0321285D84891FDD3948297E67E78AC7C78E2439579DEF0C89`

Recovered via UEAESKeyFinder (File mode) from `KillerInPurple-Win64-Shipping.exe`.

## Extraction
`repak --aes-key 0x741E... unpack KillerInPurple-WindowsNoEditor.pak --output Extracted`

Yields 10,372 files, ~4.15 GB. Bulk cooked assets (`.uasset`/`.uexp`/`.umap`) are excluded from this repo due to size; re-run the command above to regenerate them locally.
