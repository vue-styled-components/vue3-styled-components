<div align="center">
  <img alt="Owner avatar" src="https://vue-styled-components.com/logo.png" width="220px" />
  <h1>Vue Styled Components</h1>
  A CSS tool similar to styled-components and support for vue 3. Help you to develop your apps fastly!

  <br>
  <br>

  [![CI status][github-action-image]][github-action-url]
  [![NPM version][npm-version]][npm-url]
  [![minified size][npm-bundle-size]][npm-url]
  [![Coverage Status][coverage]][codecov-url]
  [![chat on discord][discord]][discord-url]

  [github-action-image]: https://github.com/v-vibe/vue-styled-components/workflows/Code%20Check/badge.svg
  [github-action-url]: https://github.com/v-vibe/vue-styled-components/actions/workflows/code-check.yml
  [npm-version]: https://img.shields.io/npm/v/%40vvibe%2Fvue-styled-components
  [npm-bundle-size]: https://img.shields.io/bundlejs/size/%40vvibe%2Fvue-styled-components
  [npm-url]: http://npmjs.org/package/@vvibe/vue-styled-components
  [coverage]: https://coveralls.io/repos/github/v-vibe/vue-styled-components/badge.svg?branch=main
  [codecov-url]: https://coveralls.io/github/v-vibe/vue-styled-components?branch=main
  [discord]: https://img.shields.io/badge/chat-on%20discord-7289da.svg?sanitize=true
  [discord-url]: https://discord.gg/UbJxnvt2UH


[Changelog](./CHANGELOG.md) · English · [中文](./README.zh_CN.md)
 
  
</div>

## ✨Feature

✅ Style vue component or styled component

✅ Set default attrs

✅ Passed props

✅ Support theming

✅ Generate keyframes

✅ Generate css mixin

✅ Create global style

✅ Add or override attrs

✅ Support nesting css. (web only: https://drafts.csswg.org/css-nesting/#nesting)

## 📖Documentation

For detailed introduction and usage instructions, please refer to [the documentation website](https://vue-styled-components.com)

## 🚀Getting Start

### 📦Install

```sh
npm i @vvibe/vue-styled-components
```

```sh
yarn add @vvibe/vue-styled-components
```

```sh
pnpm i @vvibe/vue-styled-components
```

### 💅Basic

```vue
<script setup lang="ts">
import { styled } from '@vvibe/vue-styled-components';
import OtherComponent from './VueComponent.vue';

const StyledDiv = styled('div')`
  width: 100px;
  height: 100px;
  background-color: #ccc;
  color: #000;
`;
const StyledStyledDiv = styled(StyledDiv)`
  width: 100px;
  height: 100px;
  background-color: #000;
  color: #fff;
`;
const StyledOtherComponent = styled(OtherComponent)`
  width: 100px;
  height: 100px;
  background-color: red;
  color: #fff;
`;
</script>

<template>
  <StyledDiv>Styled Div</StyledDiv>
  <StyledStyledDiv>Styled Styled Div</StyledStyledDiv>
  <StyledOtherComponent>Styled Other Vue Component</StyledOtherComponent>
</template>
```

### 🔧Attrs Setting

```vue
<script setup lang="ts">
import { styled } from '@vvibe/vue-styled-components';

const StyledDiv = styled.div.attrs({
  class: 'styled-div'
})`
  width: 100px;
  height: 100px;
  background-color: #ccc;
  color: #000;
`;
</script>

<template>
  <StyledDiv>Styled Div</StyledDiv>
  <!-- <div class="styled-div">Styled Div</div> -->
</template>
```

### 🕹️Control Dynamic Style by Props

You must define the props in the `styled` function if you want to use them in the style. Because Vue components
require explicit props declaration so that Vue knows what external props passed to the component should be treated as
fallthrough attributes.(see [Props Declaration](https://vuejs.org/guide/components/props.html#props-declaration))

```vue
<script setup lang="ts">
import { styled } from '@vvibe/vue-styled-components';

const StyledDiv = styled('div', {
  color: String
})`
  width: 100px;
  height: 100px;
  background-color: #ccc;
  color: ${(props) => props.color};
`;
</script>

<template>
  <StyledDiv color="red">Styled Div</StyledDiv>
</template>
```

### 🧙Theming

```vue
<script setup lang="ts">
import { styled, ThemeProvider } from '@vvibe/vue-styled-components';

const StyledDiv = styled.div`
  width: 100px;
  height: 100px;
  background-color: #ccc;
  color: ${(props) => props.theme.color};
`;
</script>

<template>
  <ThemeProvider :theme="{ color: '#fff' }">
    <StyledDiv>Styled Div</StyledDiv>
  </ThemeProvider>
</template>
```

**More details see [docs site](https://v-vibe.github.io/vue-styled-components/)**

## 🧑‍🤝‍🧑Contributors

<a href="https://github.com/v-vibe/vue-styled-components/graphs/contributors">
  <img alt="contributor list" src="https://contrib.rocks/image?repo=v-vibe/vue-styled-components" />
</a>

<br>

And thanks [styled-components](https://github.com/styled-components).
