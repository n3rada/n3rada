<img src="https://my-badges.github.io/my-badges/fix-6.png" alt="I did 6 sequential fixes." title="I did 6 sequential fixes." width="128">
<strong>I did 6 sequential fixes.</strong>
<br><br>

Commits:

- <a href="https://github.com/n3rada/mssqlclient-ng/commit/3a1e08b04499a417f7db585616943eaa149ad170">3a1e08b</a>: fix: restore register_action and get_action_type used in tests

Previous commit incorrectly removed these as "dead code"; both are
called by test_action_factory.py. Restore them.
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/3bc9404afca53875cb7c9669360013897ce880db">3bc9404</a>: fix: Pylance errors + dead code in kill.py, factory.py, base.py

kill.py:
- Chain ValueError re-raise with "from exc"
- Fix return type to Optional[object] to match BaseAction.execute
- Add type: ignore comments on _target usage after Arg binding

factory.py:
- Fix aliases param from List[str] = None to Optional[List[str]] = None
- Remove dead register_action (never called)
- Remove dead get_action_type (never called)

base.py:
- Remove dead parse_arguments (never called from outside)
- Remove dead get_help (never called)
- Remove now-unused "import re"
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/6f4702d1e05b5280a66d70ba8bbce275e237a6c0">6f4702d</a>: fix: createuser.py bug + remove dead argument_list param everywhere

creatuser.py had a silent bug: execute_non_processing without silent=True
swallows the SQL exception and returns -1. The re-raised RuntimeError
contained "create_login_failed" which never matched the "already exists"
pattern, so the password-update fallback was unreachable. Fix by passing
silent=True so the real SQL exception propagates to the handler.

Also:
- Remove dead argument_list=None param from validate_arguments in all
  action files (base class signature was already cleaned up)
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/6ef953060ad1855c5042c8a01626ec8e2633d443">6ef9530</a>: fix: resolve Pylance errors in linkmap.py

- Add assert _root_node is not None at the top of _display_tree,
  _format_chain_progress, _build_chain_row, _build_escalation_row
  so Pylance narrows Optional[ServerNode] to ServerNode
- Replace server_link_upper with _ in unpacking loop (unused variable)
- Chain the re-raised ValueError with "from e" in validate_arguments
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/86349ac0cd4da5f79d25118b83b5bfd1899632d8">86349ac</a>: fix: resolve Pylance type errors in terminal.py

- _switch_history: accept Optional[str] and early-return on None,
  fixing "str | None is not assignable to str" at both call sites
- Assert _prompt_session is not None before the main loop to narrow
  Optional[PromptSession] and fix attribute-access-on-None errors
- Rename unused command_line params to _command_line in handlers
  that do not use the argument (_handle_debug, _handle_unlink_all,
  _handle_revert, _handle_unlink)
- <a href="https://github.com/n3rada/mssqlclient-ng/commit/7787419297df07531d5447e7c75087b4ce81161f">7787419</a>: fix: remove dead methods and sanitize user param in can_impersonate

- Remove get_user_database_roles: never called anywhere
- Remove clear_admin_cache: subset of clear_caches(), never called
- Remove clear_admin_cache_for_server: never called anywhere
- Escape single quotes in can_impersonate user param, consistent
  with impersonate_user which already used safe_user


Created by <a href="https://github.com/my-badges/my-badges">My Badges</a>