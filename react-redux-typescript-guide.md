# React & Redux in TypeScript - Static Typing Guide

- [origin](https://github.com/piotrwitek/react-redux-typescript-guide)

> "This guide is a living compendium documenting the most important patterns and recipes on how to use React (and its Ecosystem) in a functional style with TypeScript and to make your code completely type-safe while focusing on a conciseness of type annotations so it's a minimal effort to write and to maintain types in the long run."

このガイドは、以下の最も重要なパターンとレシピの摘要ドキュメントである
> - どうReactをTypeScriptでfunctional styleで使用するかの方法
> - Typeアノテーションに焦点を当てながら、コードを完全にType-safeにする方法
> - これらを成し維持する最小限の努力

## ゴール

> - 完全なtype safety(with --strict flag) 
> - **タイプ推論**や**コントロールフロー分析**などの高度なTypeScript言語機能を使用して、タイプの冗長性を排除してTypeアノテーションを簡潔にする
> - TypeScriptに焦点を当てた補完的ライブラリを使用して、型の繰り返しと複雑さを減らす