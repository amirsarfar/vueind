# vueind

A project made for my personal everyday use, powered by Vue 3 and Tailwindcss !

## Goal

Create reusable components to be used in other projects

## Project setup

```bash
npm install
```

### Compiles and hot-reloads for development

```bash
npm run serve
```

### Compiles and minifies for production

```bash
npm run build
```

## Currently available components

- Form
  - Input

## Form

### Input

Located at ` src/components/form/ `

Props:

- type (String)
- name (String)
- label (String)
- value (String)
- required (Boolean)
- pattern (Regex string)

Usage:

```HTML
<Input name="lastname" type="text" label="Last Name" value="Sarfarazi"></Input>
```
