# battle-sim-logs

Raw match replay logs copied from the hosted battle-sim VPS. This archive contains
13 matches, including the five originally archived.

Last updated at **2026-09-17T17:01:06.199889+00:00**. The selected logs all have terminal
end records; an aborted match is included as recorded. The archive is updated manually.
This export includes completed matches found at the time of inspection.

## Matches

Times below are Europe/Amsterdam (CEST, UTC+02:00), newest first.

| Match start | Players | Final tick | Outcome | Winner | Raw replay | Build metadata |
| --- | ---: | ---: | --- | --- | --- | --- |
| 2026-09-17 18:55:08 | 8 | 2970 | winner (last_survivor) | player02 | [JSONL](matches/match_main_1789664108585187451_1_32.jsonl) | [JSON](matches/match_main_1789664108585187451_1_32.build.json) |
| 2026-09-17 18:51:46 | 9 | 931 | winner (last_survivor) | player02 | [JSONL](matches/match_main_1789663906748149880_1_27.jsonl) | [JSON](matches/match_main_1789663906748149880_1_27.build.json) |
| 2026-09-17 18:48:03 | 9 | 432 | winner (last_survivor) | player03 | [JSONL](matches/match_main_1789663683852151491_1_25.jsonl) | [JSON](matches/match_main_1789663683852151491_1_25.build.json) |
| 2026-09-17 18:46:12 | 9 | 412 | winner (last_survivor) | player03 | [JSONL](matches/match_main_1789663572518039344_1_23.jsonl) | [JSON](matches/match_main_1789663572518039344_1_23.build.json) |
| 2026-09-17 18:35:49 | 8 | 523 | winner (last_survivor) | player03 | [JSONL](matches/match_main_1789662949600755973_1_18.jsonl) | [JSON](matches/match_main_1789662949600755973_1_18.build.json) |
| 2026-09-17 18:34:36 | 8 | 492 | winner (last_survivor) | player03 | [JSONL](matches/match_main_1789662876753529152_1_16.jsonl) | [JSON](matches/match_main_1789662876753529152_1_16.build.json) |
| 2026-09-17 18:33:11 | 8 | 619 | winner (last_survivor) | player06 | [JSONL](matches/match_main_1789662791924709686_1_14.jsonl) | [JSON](matches/match_main_1789662791924709686_1_14.build.json) |
| 2026-09-17 18:31:37 | 9 | 680 | winner (last_survivor) | player01 | [JSONL](matches/match_main_1789662697187007138_1_12.jsonl) | [JSON](matches/match_main_1789662697187007138_1_12.build.json) |
| 2026-09-17 18:19:16 | 7 | 342 | winner (last_survivor) | player03 | [JSONL](matches/match_main_1789661956803650993_1_10.jsonl) | [JSON](matches/match_main_1789661956803650993_1_10.build.json) |
| 2026-09-17 18:12:48 | 6 | 501 | winner (last_survivor) | player01 | [JSONL](matches/match_main_1789661568083026030_1_8.jsonl) | [JSON](matches/match_main_1789661568083026030_1_8.build.json) |
| 2026-09-17 18:11:33 | 6 | 247 | winner (last_survivor) | player05 | [JSONL](matches/match_main_1789661493797660899_1_6.jsonl) | [JSON](matches/match_main_1789661493797660899_1_6.build.json) |
| 2026-09-17 17:52:20 | 6 | 1902 | aborted (operator_abort) | — | [JSONL](matches/match_main_1789660340953783703_1_1.jsonl) | [JSON](matches/match_main_1789660340953783703_1_1.build.json) |
| 2026-09-16 19:09:24 | 8 | 3000 | draw (timeout) | — | [JSONL](matches/match_main_1789578564136489528_1_6.jsonl) | [JSON](matches/match_main_1789578564136489528_1_6.build.json) |

## Contents and fidelity

- `matches/*.jsonl`: the complete original server replay files, byte for byte.
- `matches/*.build.json`: the matching original server build metadata.
- [manifest.json](manifest.json): source timestamps, match outcomes, original player names, file sizes, and VPS SHA-256 hashes.
- [SHA256SUMS](SHA256SUMS): checksums for all 26 source files and the manifest.

Player names are **unsanitized and unchanged**. These source logs record numbered
identities such as `player01`; those values are kept exactly as written by the
server. No real-name mappings were inferred or substituted. The original match
configuration, simulation seed, spawn data, commands, disconnect events, and end
records are retained. Git is configured to preserve the raw files without newline
conversion.

These JSONL files are the server’s authoritative match-input replay logs, not
container stdout/stderr or the SDK’s filtered bot-view recordings. Empty command
windows may be omitted by the server. A fire field is a shot request; it does not
alone prove the shot succeeded.

## Verify the download

From the repository root on Linux:

```sh
sha256sum --check SHA256SUMS
```

On macOS:

```sh
shasum -a 256 -c SHA256SUMS
```

The hashes of the raw files were calculated on the VPS and verified again after
copying and staging. All 13 replay files parsed successfully and contained a header
and terminal end record.

## Related repositories

- [battle-sim server](https://github.com/wilfredluijk/battle-sim)
- [.NET SDK](https://github.com/wilfredluijk/battle-sim-dotnet-sdk)
