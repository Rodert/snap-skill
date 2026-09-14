<p align="center">
  <img src="assets/snap-skill-logo.png" alt="Snap Skill logo" width="840">
</p>

# snap-skill

[中文](README.md) | English

> Teach AI to take a candid photo, not stage a portrait.

A multilingual candid photography skill that turns a short request into a natural-looking image prompt with believable action, camera placement, foreground occlusion, imperfect composition, and subtle photographic flaws.

Supported languages: Chinese, English, Japanese, Korean, Russian, French, and Spanish.

```text
$snap-skill A woman has just walked out of a convenience store after the rain, 9:16
```

State who and where; Snap Skill fills in the action, camera position, composition, lighting, and one to three subtle imperfections. Explicit user constraints always win. After returning a prompt, it can list the image-generation capabilities actually available in the current session and ask whether to generate now.

## Install

### Paste This Into Your Agent

Send the following block to Codex Cloud, Claude Code, Work Buddy, or any Skill-capable agent:

```text
Install the Snap Skill from https://github.com/Rodert/snap-skill.

Use your supported skill-installation workflow to install the repository as `snap-skill`. Keep the repository directory intact, including SKILL.md, references/, and assets/. Enable the skill for this workspace or session, then confirm that it can be invoked with:

$snap-skill A woman has just walked out of a convenience store at night, 9:16
```

### Local Installation

**Codex**

```bash
git clone https://github.com/Rodert/snap-skill.git ~/.codex/skills/snap-skill
```

**Claude Code**

```bash
git clone https://github.com/Rodert/snap-skill.git ~/.claude/skills/snap-skill
```

Restart the agent or begin a new session after installation, then invoke `$snap-skill`. For any other skill directory, use the paste-in instruction above and let the agent use its supported installation flow.

## Preview Gallery

<p align="center">
  <img src="assets/gallery/stairwell-rail.png" alt="Stairwell candid with railing occlusion" width="31%">
  <img src="assets/gallery/convenience-freezer.png" alt="Convenience-store freezer candid" width="31%">
  <img src="assets/gallery/glasshouse-closeup.png" alt="Natural portrait in a glasshouse" width="31%">
</p>
<p align="center">
  <img src="assets/gallery/stairwell-overhead.png" alt="Overhead stairwell candid" width="31%">
  <img src="assets/gallery/stairwell-crop.png" alt="Partially occluded stairwell candid" width="31%">
  <img src="assets/gallery/convenience-low-angle.png" alt="Low-angle convenience-store candid" width="31%">
</p>
<p align="center">
  <img src="assets/gallery/glasshouse-window.png" alt="Glasshouse window portrait" width="31%">
  <img src="assets/gallery/convenience-exit.png" alt="Rainy convenience-store exit candid" width="31%">
  <img src="assets/gallery/convenience-rain.png" alt="Convenience-store candid in the rain" width="31%">
</p>

## Natural-language controls

```text
$snap-skill Make it more raw.
$snap-skill Keep this person, make the rest random.
$snap-skill Generate five prompt-only variations.
$snap-skill Make it feel like a phone snapshot.
```

Users may write in any supported language. Every result includes matching Chinese and English prompts generated from the same photography plan; there are no duplicated language-specific skills. Asking for prompt-only output suppresses the generation follow-up.

See [SKILL.md](SKILL.md) for the complete behavior.
