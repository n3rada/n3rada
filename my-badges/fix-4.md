<img src="https://my-badges.github.io/my-badges/fix-4.png" alt="I did 4 sequential fixes." title="I did 4 sequential fixes." width="128">
<strong>I did 4 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/n3rada/mssqlclient-ng/commit/737b11dac4b0a5dd17cf42436d727106a992f3b4">737b11d</a>: fix(terminal): suppress SQL highlighting for !action lines

Use a prefix-aware lexer wrapper so action commands like !impersonation-map
are rendered in a single uniform colour instead of having SQL keywords
(e.g. "impersonation") highlighted mid-name.
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/dd800362f743b067a0e436a7b58960404353334c">dd80036</a>: fix(completions): remove category display entirely

Completion menu now shows action name on the left and plain description
on the right, with no category label.
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/03402920c1fc6d632af387beb9c70a627ca7b5b6">0340292</a>: fix(completions): move category to display_meta, keep display as plain action name

Left column shows the action name cleanly.
Right column shows [label] description, e.g. [db] List all databases.

Category labels: admin, agent, cm, db, domain, exec, fs, remote.
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/1a66ae8fcc77ee4c544ae9cd2bd2cfec4706e13d">1a66ae8</a>: fix(filesystem): fix undefined argument_list in tree.py validate_arguments


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>