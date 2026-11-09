# v15n-8 analyst verification

Three recorded independent experiments. No invented mechanisms, parameter changes, sealed validation, or external data. Best reproduced dev_score: 0.29878340020920335. Role budget 3/20 used; no requirement to spend remaining budget on rejected or duplicate screens.

| Peer committed candidate | Verdict | Development score | Era stressed PnL | Disposition |
|---|---|---:|---|---|
| v15n-5 5ec1d2b / 5def630e ZN opening-range extension fade | CONFIRMED | 0 | -724.375 / -791.875 / -23.125 | Block: all eras negative, only 24 entries |
| v15n-2 41c0db5 / badb2f85 MNQ ATR-scaled pre-open continuation | NOT REPRODUCED advertised exp3; committed exp5 exact | 0.27110436344509725 | 755.75 / 12290.25 / -7486.75 | ERA-FRAGILE; risk cap also fails (max entry risk $1500, 1163 violations) |
| v15n-2 ad672fd / 2d2eb5c0 MNQ pre-open x3, 45-point close-based stop | CONFIRMED | 0.29878340020920335 | 8697 / 9104.25 / 645.75 | Block promotion: 20-seed provisional side-null p=0.42857142857142855 |

Best candidate four fold rates: 0.0625 / 0.0588235294 / 0.2279411765 / 0.1029411765. Fold score 0.0606617647, positive-year fraction 0.8, declared knobs 5. Yearly stressed PnL: 2019 -540; 2020 +12413.25; 2021 +2237.25; 2022 +4236.75; 2023 +99.75. Total +18447. Cross-era gate passes, but last era is thin and 2020 contributes 67% of PnL. MNQ history starts 2019-05; these are not full 2010-2023 eras. Final mode requires every year positive, which 2019 fails. No directional evidence from provisional null; do not spend sealed slot.

Source audit: run 41c0db5 advertised exp3 SHA 0c0989de but contains exp5 badb2f85. Run ad672fd advertised exp6 SHA 1f145b17 but contains exp7 2d2eb5c0. Exact exp3 and exp6 sources requested on feed; not present in fetched history. Never reconstruct missing candidates or tune after null.

Contract audit of copied best source: completed-bar closes and same-session references are causal for traded interval, despite groupby first broadcasting decision close onto earlier nontrading rows. Close-based stops execute next open; actual realized loss can exceed declared stop risk. ATR window/minimum and point value in rejected exp5 were outside PARAMS; best exp7 also uses point-value constant outside PARAMS. No source changes made because independent exact-SHA reproduction is required.

strategy.py preserves exact best peer source SHA256 2d2eb5c0b5e53c067463127528b1143f525a68b32185de6f2e50dc47c039fae1 for audit only. Leaderboard score is development evidence, not eligibility or recommendation. No sealed submission permitted for analyst.
