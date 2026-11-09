# v15n-8 analyst verification

Five recorded independent experiments (three screens, two direct 20-seed provisional-null runs). No invented mechanisms, parameter changes, sealed validation, or external data. Best reproduced dev_score: 0.29878340020920335. Role budget 5/20 used; no requirement to spend remaining budget on rejected or duplicate screens.

| Peer committed candidate | Verdict | Development score | Era stressed PnL | Disposition |
|---|---|---:|---|---|
| v15n-5 5ec1d2b / 5def630e ZN opening-range extension fade | CONFIRMED | 0 | -724.375 / -791.875 / -23.125 | Block: all eras negative, only 24 entries |
| v15n-2 41c0db5 / badb2f85 MNQ ATR-scaled pre-open continuation | NOT REPRODUCED advertised exp3; committed exp5 exact | 0.27110436344509725 | 755.75 / 12290.25 / -7486.75 | ERA-FRAGILE; risk cap also fails (max entry risk $1500, 1163 violations) |
| v15n-2 ad672fd / 2d2eb5c0 MNQ pre-open x3, 45-point close-based stop | CONFIRMED | 0.29878340020920335 | 8697 / 9104.25 / 645.75 | Block promotion: 20-seed provisional side-null p=0.42857142857142855 |

Best candidate four fold rates: 0.0625 / 0.0588235294 / 0.2279411765 / 0.1029411765. Fold score 0.0606617647, positive-year fraction 0.8, declared knobs 5. Yearly stressed PnL: 2019 -540; 2020 +12413.25; 2021 +2237.25; 2022 +4236.75; 2023 +99.75. Total +18447. Cross-era gate passes, but last era is thin and 2020 contributes 67% of PnL. MNQ history starts 2019-05; these are not full 2010-2023 eras. Final mode requires every year positive, which 2019 fails. No directional evidence from provisional null; do not spend sealed slot.

Source audit: run 41c0db5 advertised exp3 SHA 0c0989de but contains exp5 badb2f85. Run ad672fd advertised exp6 SHA 1f145b17 but contains exp7 2d2eb5c0. Exact exp3 and exp6 sources requested on feed; not present in fetched history. Never reconstruct missing candidates or tune after null.

Contract audit of copied best source: completed-bar closes and same-session references are causal for traded interval, despite groupby first broadcasting decision close onto earlier nontrading rows. Close-based stops execute next open; actual realized loss can exceed declared stop risk. ATR window/minimum and point value in rejected exp5 were outside PARAMS; best exp7 also uses point-value constant outside PARAMS. No source changes made because independent exact-SHA reproduction is required.

strategy.py preserves exact best peer source SHA256 2d2eb5c0b5e53c067463127528b1143f525a68b32185de6f2e50dc47c039fae1 for audit only. Leaderboard score is development evidence, not eligibility or recommendation. No sealed submission permitted for analyst.

## Additional verification

* v15n-3 d09d6e2, source ecfa104a8153001a617d246b6e5c46e4ea3fef449e8eb1889b9900635da74900: CONFIRMED dev_score 0.2982990337831843, folds 0.0551470588/0.0698529412/0.2132352941/0.1323529412, era PnL 1746.75/9381/1789.5. Year PnL 2019 -4870.5, 2020 +9646.5, 2021 +3951, 2022 +3229.5, 2023 +960.75. Direct 20-seed provisional null p=0.42857142857142855, fails. Seeds shared with other candidate: not independent statistical confirmation. Do not promote.
* v15n-1 5959061, source 5289be6fe0b8227e0c07f140df06024c3d24a93a02c7f1b54720d1f3d90c4fb5: CONFIRMED dev_score 0.25808461646436776, folds 0.0441176471/0.0698529412/0.2316176471/0.0772058824, eras 4257/8121/2283. Year PnL 2019 -2748, 2020 +9987.75, 2021 +2151, 2022 +6159, 2023 -888.75. Blocked positive-year fraction 0.6 < 0.7. No null spent.

Final ranking: v15n-2 exp7 0.298783 > v15n-3 replay 0.298299 > v15n-2 exp5 0.271104 (era and risk failure) > v15n-1 replay 0.258085 > v15n-5 sparse fade 0. All blocked for promotion. Best remains experiment 3; two subsequent experiments without improvement. Stop voluntarily below ceiling: remaining committed useful candidates exhausted; peers completed and no new eligible mechanism to audit. No claim of eight-experiment stagnation. No sealed submissions.

Saved raw local reports under ignored peers/. Full per-experiment development metrics, folds, eras, years, gates and provisional null results are committed in experiments.jsonl. Source best peer candidate remains byte-identical in strategy.py. Development leaderboard submission 63332ee7 uses reproduced dev_score, not eligibility-gated score.
