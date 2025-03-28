<rules>
1- always use latest version of dependencies.
2- use app router
3- write in typescript
4- use the given eslint rules as eslint
5- make sure it structered well, 
6- let me write folder bash command do not make yourself
</rules>
<eslint_rules>
{
  "env": {
    "browser": true,
    "es2021": true,
    "node": true
  },
  "plugins": ["@typescript-eslint", "simple-import-sort", "unused-imports"],
  "extends": [
    "eslint:recommended",
    "next",
    "next/core-web-vitals",
    "plugin:@typescript-eslint/recommended",
    "prettier",
    "plugin:storybook/recommended",
    "plugin:tailwindcss/recommended"
  ],
  "rules": {
    "no-unused-vars": "off",
    "tailwindcss/no-custom-classname": "off",

    "no-console": "warn",
    "@typescript-eslint/explicit-module-boundary-types": "off",
    "react/no-unescaped-entities": "off",

    "react/display-name": "off",
    "react/jsx-curly-brace-presence": [
      "warn",
      { "props": "never", "children": "never" }
    ],

    //#region  //*=========== Unused Import ===========
    "@typescript-eslint/no-unused-vars": "off",
    "unused-imports/no-unused-imports": "warn",
    "unused-imports/no-unused-vars": [
      "warn",
      {
        "vars": "all",
        "varsIgnorePattern": "^_",
        "args": "after-used",
        "argsIgnorePattern": "^_"
      }
    ],
    //#endregion  //*======== Unused Import ===========

    //#region  //*=========== Import Sort ===========
    "simple-import-sort/exports": "off",
    "simple-import-sort/imports": [
      "warn",
      {
        "groups": [
          // ext library & side effect imports
          ["^@?\\w", "^\\u0000"],
          // {s}css files
          ["^.+\\.s?css$"],
          // Lib and hooks
          ["^@/lib", "^@/hooks"],
          // static data
          ["^@/data"],
          // components
          ["^@/components", "^@/container"],
          // zustand store
          ["^@/store"],
          // Other imports
          ["^@/"],
          // relative paths up until 3 level
          [
            "^\\./?$",
            "^\\.(?!/?$)",
            "^\\.\\./?$",
            "^\\.\\.(?!/?$)",
            "^\\.\\./\\.\\./?$",
            "^\\.\\./\\.\\.(?!/?$)",
            "^\\.\\./\\.\\./\\.\\./?$",
            "^\\.\\./\\.\\./\\.\\.(?!/?$)"
          ],
          ["^@/types"],
          // other that didnt fit in
          ["^"]
        ]
      }
    ]
    //#endregion  //*======== Import Sort ===========
  },
  "globals": {
    "React": true,
    "JSX": true
  }
}
</eslint_rules>
