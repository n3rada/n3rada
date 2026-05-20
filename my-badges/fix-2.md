<img src="https://my-badges.github.io/my-badges/fix-2.png" alt="I did 2 sequential fixes." title="I did 2 sequential fixes." width="128">
<strong>I did 2 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/n3rada/mssqlclient-ng/commit/3796a8d2d07af0f4cc027f34584a9fc2e298929b">3796a8d</a>: fix(adsi): narrow get_adsi_server_names return type to list[str]

Use isinstance walrus filter to satisfy the list[str] return annotation.
Remaining changes are blank-line formatting applied by the editor.
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/c0f31e4972a468abca914f9af2dca0f053069f62">c0f31e4</a>: fix: resolve runtime NameErrors from type hint migration

- Add 'from __future__ import annotations' to linked_servers.py to
  make the forward reference 'LinkedServers' valid in | unions
- Rewrite ActionResult alias using | instead of Union[...]
- Replace bare unparameterised Dict/List/Tuple/Set/Type with
  their built-in equivalents across 47 files

All 491 tests pass.


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>