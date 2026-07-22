# TypeScript : Configuration

## Strict Configuration

```json
{
  "compilerOptions": {
    "target": "ES2023",
    "module": "NodeNext",
    "moduleResolution": "NodeNext",
    "rootDir": "src",
    "outDir": "dist",
    "strict": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,
    "noImplicitOverride": true,
    "noFallthroughCasesInSwitch": true,
    "verbatimModuleSyntax": true,
    "declaration": true,
    "sourceMap": true,
    "skipLibCheck": true
  },
  "include": ["src/**/*.ts"],
  "exclude": ["dist", "node_modules"]
}
```

## Inspect Configuration

```bash
npx tsc --showConfig
npx tsc --listFiles
npx tsc --explainFiles
npx tsc --traceResolution
```

## Project References

```json
{
  "files": [],
  "references": [
    { "path": "./packages/core" },
    { "path": "./packages/application" }
  ]
}
```
