# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.3.0] - 2026-09-26

### Added
- 同域候选从 3 条放大到至少 7 条（用户校验样本量）
- 输出改表格化：候选｜它是什么｜为什么像｜上手难度｜质量信号
- 新增"入门路径"：先从这一个开始 → 再读那个
- 新增总标签：给这组品味起有记忆点的名字
- 领域按用户输入动态分块，不再预设书影音
- skill-card.md 发布卡片
- EVAL-REPORT.md 最终评测报告（NVIDIA 5 维 90/100、agent-creator 7 维 70/70、自有 6 维 12/12）

### Changed
- 跨域每类固定 3 个（稳妥 2 + 冒险 1）
- tags 去掉 books/movies/music 预设感，改为通用 recommendation
- 质量自查清单更新到 11 项

### Fixed
- 无（v0.2.3 已清理 TasteDive / Google Books / iTunes movie 不可用接口）

## [0.2.3] - 2026-09-25

### Removed
- TasteDive（Cloudflare 403 拦截）
- Google Books（429 限流）
- iTunes movie（恒返 0，不可靠）

### Added
- OpenLibrary 书存在性核实
- iTunes Search 音乐存在性核实
- Wikidata 电影存在性核实（按 description 含 "film" 区分同名）
- TVmaze 剧集存在性核实（备用）

## [0.2.0] - 2026-09-24

### Added
- 跨域品味画像核心流程
- 3 轮自进化评测循环（v0.2.0=9 → v0.2.1=11 → v0.2.2=12）
- 稳妥款/冒险款分档
- NEVER 清单

## [0.1.0] - 2026-09-23

### Added
- 基础书影音推荐
- TasteDive + OpenLibrary 初版召回
