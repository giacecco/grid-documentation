---
slug: comment
title: Comment
tags: [Action Block, LUA, Workflow]
---

Comment blocks are used to create comments in Editor for creating notes and general comments. These comments are saved onto Grid when the configuration is stored.

Comments are useful for making notes about functionality within a configuration or naming parts of an Action Chain. But be careful, comments eat up the per Event [characterlimit](../../char-limit) of Grid configurations very quickly, so use them sparingly!

:::caution
Comments used inside of Code Blocks with the generic `---comment` lua syntax will be deleted on a commit.
:::