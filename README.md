[![NPM](https://img.shields.io/npm/v/slidev-addon-rabbit)](https://www.npmjs.com/package/slidev-addon-rabbit)
# slidev-addon-rabbit

Presentation time management for slidev inspired by [rabbit\-shocker/rabbit](https://github.com/rabbit-shocker/rabbit/) | [Rabbit \- はじめに](https://rabbit-shocker.org/ja/)

# Demo

https://kaakaa.github.io/slidev-addon-rabbit/1?time=1

![](./assets/screen.gif)

## Description

As the presentation begins, the rabbit and the turtle aim for the goal. **The rabbit** represents **the current page**, and **the turtle** represents **the elapsed time** since the start. Let's guide the rabbit to the goal before the turtle arrives, ensuring everyone has enough leisure time.

![](./assets/description.png)

## Usage

1. Apply `slidev-addon-rabbit` to your slidev project
   - See [Use Addon \| Slidev](https://sli.dev/addons/use.html)
2. Run slidev (e.g.: `npm run dev`)
3. Attach url query `?time=10` to presentation url, and access it
   - e.g.: `http://localhost:3030/?time=10`

## Configs


```yaml
---
...
addons:
  - slidev-addon-rabbit
rabbit:
  slideNum: true   # Show current/total slide numbers next to a rabbit icon
...
---
```

# License

This repository distributes under [MIT License](./LICENSE)

Icons used in this slide are distributed from [Emoji One \(Monotone\)](https://icon-sets.iconify.design/emojione-monotone/) under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.ja).

