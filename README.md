<p align="center">
  <img src="assets/snap-skill-logo.png" alt="抓拍 skill 标志" width="840">
</p>

# snap-skill

中文 | [English](README.en.md)

> 让 AI 学会抓拍，而不是摆拍。

一个让 AI 学会“抓拍”的多语言摄影 Skill。它将一句自然语言描述转化为具有真实生活感、偶然抓拍感和自然摄影缺陷的人像摄影提示词。

支持：中文、English、日本語、한국어、Русский、Français、Español。

```text
$snap-skill 一个女生从便利店出来，夜晚，9:16
```

你只管说拍谁、在哪儿；动作、机位、遮挡、构图和少量成像瑕疵由 Skill 补全。明确指定的条件始终优先。

## 可以这样说

```text
$snap-skill 便利店门口，韩系女生，夜晚
$snap-skill 随机来一张
$snap-skill 用这个人物，换成雨天街头抓拍
$snap-skill 生成 5 组，只要提示词
```

也支持口语调整：`更野一点`、`更像路人拍的`、`更真实`、`更像手机拍的`、`固定人物，其他随机`。输入和输出会自动跟随用户的主要语言。

## 同一个 Skill，七种语言

```text
🇨🇳 $snap-skill 雨后的便利店门口，一个女生刚推门出来。
🇺🇸 $snap-skill A woman has just walked out of a convenience store after the rain.
🇯🇵 $snap-skill 雨上がりのコンビニから女性が出てきた瞬間。
```

所有语言进入同一套摄影规则；不维护重复的多语言规则文件。

## 设计原则

- 锁定用户明确给出的主体、场景、画幅、衣着、焦段和风格。
- 用未完成动作、真实摄影者位置和自然遮挡建立偶然感。
- 默认避免居中摆拍、影棚灯光、过度磨皮和完美构图。
- 每张图只使用 1 至 3 种轻微成像缺陷，避免堆砌效果。

详见 [SKILL.md](SKILL.md)。
