# D26 Managed Post-Reattach Exit Convergence

Status: the final reviewed implementation candidate is locally and
declared-Rust-1.88 validated and installed byte-identically for operator
inspection. The live-falsified OpenCode 1.18.29 sequence and an
operator-reviewed Codex 0.153.4 sequence passed on the pre-review candidate;
that acceptance is not attributed to the final artifact, whose live
reacceptance remains open. GitHub CI run `34328413481` passes the full check and
declared Rust 1.88 jobs for implementation commit `988c006`.

## Contract exercised

D26 changes no public command, key, page, status, schema, provider traffic, or
Archive/Restore behavior. It preserves the provider-pane attachment helper as
the only handoff owner after native tmux attachment returns.

Only one typed transient can enter the new dedicated retry window: an exact
native zero-exit candidate whose recorded process group is still draining at
the final cleanup fence. Every retry reopens current state and re-proves the
Workstream and Runtime revisions, exact Runtime identity and generation,
provider identity, retained pane PID/topology/cwd/zero status, and group
emptiness. A changed revision, nonzero exit, mismatched or inaccessible
identity, malformed evidence, or every other ambiguity remains an immediate
closed refusal without signaling or mutation. The shared generic-stop timeout
is unchanged and no monitor, relaunch, pane capture, or content persistence was
added.

Review further proved that retry authority must end after the recorded group
has once been observed empty: a changed final exit proof or reappearing group
now refuses immediately. It also exposed an immediate Archive-to-Forget race
on slower Linux systems. A stopped Runtime with a missing private server now
skips redundant provider signaling only for an absent provider, or its exact
same-birth zombie, when the recorded group is empty. A live exact provider
continues through ordinary identity-proven shutdown; changed, partial,
nonempty, or unreadable evidence refuses.

## Deterministic and compatibility validation

Focused regressions cover a delayed exact OpenCode-shaped group drain that
later parks the Workstream, stops the Runtime, removes its OpenCode handle, and
removes the private Runtime artifacts. Separate cases prove a changed revision
and nonzero exit are not retryable and do not mutate state. Helper-loop tests
prove only the typed outcome retries, bounded timeout refuses, and ordinary
errors are terminal. Final-fence tests prove changed exit evidence and a
reappearing group never retry. Stopped-provider tests prove exact
absent/zombie-and-empty classification without signaling. A nested private-tmux
regression proves outer presentation detach/reattach preserves the exact inner
Runtime client and a later provider exit retains the cross-version zero-exit
candidate without inspecting pane content.

The final uninterrupted local `scripts/check` run exited zero with 435 library
tests and 11 presentation integration tests, plus formatting, strict Clippy,
packaging, dependency advisory/license/source policy, current source and CLI
acceptance, disposable presentation/state acceptance, Markdown links, and diff
checks.

A fresh `rust:1.88-bookworm` container with Rust 1.88.0, tmux 3.3a, and Zsh 5.9
passed the locked all-targets/all-features matrix serially: the same 435 library
tests and 11 presentation integration tests. The container copied only the
current source into disposable storage and was removed after the run.

GitHub CI run `34328413481` independently passed both the full `check` and
declared Rust 1.88 `msrv` jobs for implementation commit `988c006`.

Three failed review runs remain diagnosis evidence, not acceptance. The first
exposed an exact same-birth zombie between Archive and immediate Forget; the
second exposed a nested fixture assertion that depended on unreliable
`pane-died` hook delivery instead of the separately tested production fallback;
and the third exposed tmux 3.3a's known blank `pane_dead_status`. The final
nested assertion accepts only normal tmux status `0` with process absence, or
blank status with the fixture's exact same-birth zombie after its deterministic
`exit 0`. The final fresh container passed afterward.

The final locked release and installed executable are both `wsnav 0.1.0`, mode
`0755`, size 7,393,416 bytes, and SHA-256
`3bfccf4e63038174a6e92b68cdbf8103184b8d4a2f41e58055f13df278292ca7`.

## Sanitized OpenCode acceptance on the pre-review candidate

Explicitly authorized live acceptance used OpenCode 1.18.29 and tmux 3.7c with
an isolated HOME/XDG environment, disposable repository and WSNav state root,
and private tmux servers only. No provider pane, prompt, response, tool output,
transcript, credentials, or raw provider payload was read or retained.

The candidate passed the sequence that falsified D25:

- onboarding created one exact Workstream, Runtime, provider binding, OpenCode
  handle, and onboarding target;
- immediate native `/exit` converged to parked/stopped state and removed the
  handle, provider process, private server, socket, and Runtime directory;
- reopen established a stable provider identity;
- outer presentation detach/reattach preserved the same Runtime identity hash,
  provider PID/birth, generation/session, lifecycle, handle, and private
  socket; and
- a second native `/exit` after reattachment again converged to parked/stopped,
  removed the handle and private Runtime artifacts, and left no provider or
  observer process. The durable stopped row retained only bounded historical
  provider identity metadata.

Cleanup removed every disposable outer/inner tmux server, process, socket, and
root. Ordinary WSNav state retained the same three files and aggregate hash
`0f2b96d840065da902cf407723b60b9249fde232981cff2d3c1087bca70c81e3`;
default tmux session/client counts were unchanged, and no ordinary WSNav or
OpenCode process was introduced.

## Sanitized Codex acceptance on the pre-review candidate

Codex 0.153.4 acceptance used another isolated HOME/XDG environment,
repository, Codex home, WSNav state root, and private tmux hierarchy. The
operator reviewed the generated observer hooks through Codex's native surface;
WSNav then recorded the integration as ready. No provider pane or provider
content was captured or inspected.

The first native `/exit` moved the exact Workstream from open to parked and its
Runtime from starting to stopped, removed the private Runtime server/socket,
and left the recorded provider process absent. Reopening the same Workstream
started the next exact Runtime generation. Removing its outer WSNav client and
starting a fresh one preserved the same provider PID/birth, Runtime generation
and revision, Workstream revision, and private socket inode. A second native
`/exit` again reached parked/stopped and removed the private Runtime artifacts.
No work prompt was sent; Codex emitted no observed provider-session binding,
and WSNav did not fabricate one.

Cleanup stopped the exact disposable outer and presentation servers and
removed the entire acceptance root, including the mode-private authentication
copy. The root, its sockets, and every process named by its exact paths were
absent afterward. Ordinary WSNav state retained two Workstreams, two Runtimes,
two Projects, one Codex integration, and the same three-file aggregate SHA-256
`0f2b96d840065da902cf407723b60b9249fde232981cff2d3c1087bca70c81e3`.
The default tmux server retained the same four-session set and no disposable
session, and the accepted pre-review release hash remained
`02ba1bde39be9fdd0c275497a7ebfd02a40d055fd2440a54c8fc2e832f820d60`.
