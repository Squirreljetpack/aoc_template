# Setup

Install [cargo-alias-exec](https://crates.io/crates/cargo-alias-exec) and [aoc-cli](https://crates.io/crates/aoc-cli).

If you have the gh cli installed, you can use `cargo @secrets` to prompt you through the following steps:
- To get your `AOC_SESSION`: press F12 anywhere on the Advent of Code website to open your browser developer tools (Cmd+Shift+J). Look in Cookies under the Application or Storage tab, and copy out the session cookie value.
- To get your `AOC_USER_ID`: Go to [this page](https://adventofcode.com/settings) and copy the number behind the `#` symbol.
- Set the values in your github repo settings/secrets/actions
- Store your `AOC_SESSION` in `$ADVENT_OF_CODE_SESSION` or `~/.adventofcode.session`

Set the year in `.cargo/config.toml`.

Finally, edit your dependencies in Cargo.toml if you wish.

---

>[!NOTE]
> All the following aliases default to the next incomplete day if no day is given.
>
> For example, `cargo @n 3` will set up day 3, while `cargo @n` will set up the next available day.
>
> A day is considered complete when the last line of `data/puzzles/{day}.md` begins with `#` (i.e. `#complete or #skip`).

# Scaffold

- `cargo @n`: get and show the files for the next problem.
	- In case of missing files for any reason, use `cargo @refresh [n]`.

# Solve

- _write your solution!_
- `cargo @t`: test.
	- GEMINI.md comes with instructions for generating examples.

# Submit
- `cargo @s`: solve (+ benchmark).
	- If you wish to only run one part, add the part number to `advent_of_code::solution!(DAY, <1/2>)` in your source file.
- `cargo @s1/s2`: submit your solution for part 1 or 2.
	- A successful `s2` will mark the day `#complete`.
- `git push`: workflow updates the leaderboard in your README.

# Links

- https://github.com/fspoettel/advent-of-code-rust - the base template, check it out for more details! The following modifications were made:
	- simplified ci compared to the base project: only README stars are updated on push, reduced repository secrets needed.
	- added cargo aliases for workflows
	- a set of initial dependencies for solutions
	- support -P to download subcommand to only refresh puzzle
	- revised solution template
	- minor fixes
- https://adventofcode.com
