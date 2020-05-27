# AutoCorrrect for Rust

[![Build Status](https://travis-ci.org/huacnlee/auto-correct.rs.svg?branch=master)](https://travis-ci.org/huacnlee/auto-correct.rs)

Automatically add whitespace between CJK (Chinese, Japanese, Korean) and half-width characters (alphabetical letters, numerical digits and symbols).

## Other implements

- Ruby - [auto-correct](https://github.com/huacnlee/auto-correct).
- Go - [go-auto-correct](https://github.com/huacnlee/go-auto-correct).
- Rust - [auto-correct.rs](https://github.com/huacnlee/auto-correct.rs).

## Features

- Auto add spacings between CJK (Chinese, Japanese, Korean) and English words.
- HTML content support.

## Install

In your Cargo.toml

```toml
[dependencies]
autocorrect = "0.1.1"
```

## Usage

Use `autocorrect::format` to format plain text.

```rust
extern crate autocorrect;

fn main() {
    println!("{}", autocorrect::format("长桥LongBridge App下载"));
    // => "长桥 LongBridge App 下载"

    println!("{}", autocorrect::format("Ruby 2.7版本第1次发布"));
    // => "Ruby 2.7 版本第 1 次发布"

    println!("{}", autocorrect::format("于3月10日开始"));
    // => "于 3 月 10 日开始"

    println!("{}", autocorrect::format("包装日期为2013年3月10日"));
    // => "包装日期为2013年3月10日"

    println!("{}", autocorrect::format("全世界已有数百家公司在生产环境中使用Rust，以达到快速、跨平台、低资源占用的目的。"));
    // => "全世界已有数百家公司在生产环境中使用 Rust，以达到快速、跨平台、低资源占用的目的。"

    println!("{}", autocorrect::format("既に、世界中の数百という企業がRustを採用し、高速で低リソースのクロスプラットフォームソリューションを実現しています。"));
    // => "既に、世界中の数百という企業が Rust を採用し、高速で低リソースのクロスプラットフォームソリューションを実現しています。"

    println!("{}", autocorrect::format("전 세계 수백 개의 회사가 프로덕션 환경에서 Rust를 사용하여 빠르고, 크로스 플랫폼 및 낮은 리소스 사용량을 달성했습니다."));
    // => "전 세계 수백 개의 회사가 프로덕션 환경에서 Rust 를 사용하여 빠르고, 크로스 플랫폼 및 낮은 리소스 사용량을 달성했습니다."
}
```

## Benchmark

### Format

TODO

### FormatHTML

TODO

## License

This project under MIT license.
