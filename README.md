# WxMvu

[![GitHub](https://img.shields.io/badge/github-HeroesLament%2Fwx_mvu-black?logo=github)](https://github.com/HeroesLament/wx_mvu)
[![Hex.pm](https://img.shields.io/hexpm/v/wx_mvu.svg)](https://hex.pm/packages/wx_mvu)
[![Hex Docs](https://img.shields.io/hexpm/docs/wx_mvu.svg)](https://hexdocs.pm/wx_mvu)
[![Build Status](https://github.com/HeroesLament/wx_mvu/actions/workflows/ci.yml/badge.svg)](https://github.com/HeroesLament/wx_mvu/actions)
[![License](https://img.shields.io/hexpm/l/wx_mvu.svg)](https://github.com/HeroesLament/wx_mvu/blob/main/LICENSE)

MVU-based wxWidgets GUIs with integrated OpenGL rendering.

---

## Overview

WxMvu is a Model–View–Update framework for building native desktop applications
on the BEAM using wxWidgets.

It enforces a strict separation between immutable application state, pure update
logic, and declarative UI structure, while confining all direct wxWidgets calls
to a dedicated renderer process.

In addition to standard widgets, WxMvu provides a managed OpenGL canvas model for
high-throughput, real-time rendering such as scopes, waterfalls, and custom
visualizations. OpenGL canvases own their rendering loop and context, receive
data directly via message passing, and intentionally bypass MVU diffing.

The goal is not to abstract wxWidgets or OpenGL away, but to contain them within
clear ownership and lifecycle boundaries that fit naturally into OTP systems.

---

## Installation

Add `wx_mvu` to your dependencies in `mix.exs`:

```elixir
def deps do
  [
    {:wx_mvu, "~> 0.1.0"}
  ]
end
