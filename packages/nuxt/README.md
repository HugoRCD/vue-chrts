# @vue-chrts/nuxt

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]

> Nuxt module for vue-chrts

## Features

- 📊 Use beautiful chart components in your Nuxt applications
- 🔄 Auto-imports for all chart components
- 🎛️ Configure which components to include
- 🪶 Tree-shakable - only import what you use

## Installation

```bash
# npm
npm install @vue-chrts/nuxt

# yarn
yarn add @vue-chrts/nuxt

# pnpm
pnpm add @vue-chrts/nuxt
```

## Usage

Add the module to your Nuxt config:

```ts
// nuxt.config.ts
export default defineNuxtConfig({
  modules: ['@vue-chrts/nuxt'],
  
  // Optional configuration
  vueChrts: {
    // Add prefix to component names (default: 'Chrt')
    prefix: 'Chrt',
    
    // Make components globally available (default: true)
    global: true,
    
    // Only include specific components (default: all components)
    include: ['AreaChart', 'LineChart'],
    
    // Enable auto-imports (default: true)
    autoImports: true
  }
})
```

Then use the components in your Nuxt application:

```vue
<template>
  <div class="chart-wrapper">
    <ChrtLineChart 
      :data="data" 
      :height="300"
      :accessor="accessor"
      :x-axis-title="xAxisTitle"  
    />
  </div>
</template>

<script setup>
// The types are auto-imported
const data = ref([
  { date: '2023-01', value: 100 },
  { date: '2023-02', value: 200 },
  { date: '2023-03', value: 150 },
])

const accessor = (d) => d.value
const xAxisTitle = 'Month'
</script>
```

## Available Components

- `ChrtAreaChart` - Area chart
- `ChrtAreaStackedChart` - Stacked area chart
- `ChrtLineChart` - Line chart
- `ChrtBarChart` - Bar chart
- `ChrtDonutChart` - Donut chart

## Auto-imported Types

The following types are auto-imported:

- `LegendPosition`
- `CurveType`
- `Orientation`
- `BulletLegendItemInterface`

## License

MIT

<!-- Badges -->
[npm-version-src]: https://img.shields.io/npm/v/@vue-chrts/nuxt/latest.svg?style=flat&colorA=18181B&colorB=28CF8D
[npm-version-href]: https://npmjs.com/package/@vue-chrts/nuxt

[npm-downloads-src]: https://img.shields.io/npm/dm/@vue-chrts/nuxt.svg?style=flat&colorA=18181B&colorB=28CF8D
[npm-downloads-href]: https://npmjs.com/package/@vue-chrts/nuxt