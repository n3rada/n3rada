<img src="https://my-badges.github.io/my-badges/fix-2.png" alt="I did 2 sequential fixes." title="I did 2 sequential fixes." width="128">
<strong>I did 2 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/n3rada/mssqlclient-ng/commit/6fffcc513a7f0e97355d2466cff71873a4022027">6fffcc5</a>: fix: replace logger._core access with logger.disable/enable

logger._core is a private loguru attribute. Instead use the public
logger.disable("") / logger.enable("") API which silences all log
messages globally and restores the previous state on enable.

Also removes the now-unused sys import and _format_message import
(only referenced in the removed handler teardown/restore block).
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/2991ba855303eca374dceedaacfe73a542525f8c">2991ba8</a>: fix: type BaseAction.execute(Any) to resolve signature mismatch

Pylance reported W0222 on every subclass because the base declared
execute(self, database_context=None) - the default None made the inferred
type Optional[None], incompatible with DatabaseContext in overrides.

- Remove the default value, annotate with Any (avoids circular import
  that a DatabaseContext forward-ref would require)
- Fix smb_coerce return type: Optional[bool] -> Optional[object] to match
  the base class contract


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>