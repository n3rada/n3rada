<img src="https://my-badges.github.io/my-badges/fix-2.png" alt="I did 2 sequential fixes." title="I did 2 sequential fixes." width="128">
<strong>I did 2 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/n3rada/mssqlclient-ng/commit/55f7609dcd4c0416279bad80a957c72927984025">55f7609</a>: fix: resolve Pylance errors in xpcmd.py

- Narrow _command from Arg to str with explicit str() cast before use
- Cast tuple_mode result to List[Any] to avoid Dict pop(int) type error
- Replace row.pop(0) with row[0]: pop was mutating the tuple row
  unnecessarily; indexing is both correct and side-effect-free
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/c5c679e9230fb76fdf024f96c648b9f105b4e911">c5c679e</a>: fix: clean up cli.py dead code and redundant guards

- Remove three hasattr checks on args attributes that are always
  registered by argparse (std, no_log_file, kdcHost)
- Assign is_azure_sql result to _ so the intent (trigger caching)
  is explicit rather than a silent bare expression
- Remove unreachable "return 1" after the try/except/finally block
  (every code path already returns inside the try or except)


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>