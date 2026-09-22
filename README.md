# cv32e40p

PULP's CV32E40P, the RV32 core with the CORE-V extensions, taken as a black box.

![maturity](https://img.shields.io/badge/maturity-planned-lightgrey) ![license](https://img.shields.io/badge/license-MIT%20OR%20Apache--2.0%20OR%20MulanPSL--2.0-blue) ![upstream](https://img.shields.io/badge/upstream-SHL--0.51-lightgrey)

Part of the [Tape-Out](https://github.com/Tape-Out) IP library, wired up by
[`xirang`](https://github.com/Tape-Out/xirang). The core is a submodule at
`third_party/cv32e40p`; nothing in it is modified. 111 SystemVerilog files elaborate clean.

## What this repository adds

All seven parameters are knobs. Upstream declares `COREV_PULP`, `FPU` and `ZFINX` as `int`
rather than one-bit, so they arrive as integers, not switches — the manifest says `int` with
a range because that is what the design says, not what the names suggest.

Both memory ports speak OBI, PULP's own `req`/`gnt`/`rvalid` bus. That is declared, not
guessed: the declaration is checked against the elaborated design, and a port that does not
exist fails with its own check number.

## Testing

No upstream test runs here yet — CV32E40P ships no prebuilt firmware, and its verification
environment is UVM. Every matrix point still has to elaborate, and the declaration is checked
against the elaborated design each time.

## Licence, and a caveat

`third_party/cv32e40p` is under the **Solderpad Hardware License 0.51**. SHL-0.51 is *not*
an OSI-approved licence — its own text says it is based on Apache 2.0 but has neither been
approved nor endorsed by Apache. Most of the PULP family carries it. Treat it as a licence to
read before shipping silicon, not as a drop-in Apache 2.0.

This repository's own files: 任选其一 [MIT](LICENSE-MIT) · [Apache 2.0](LICENSE-APACHE) ·
[木兰宽松许可证 第2版](LICENSE-MULAN).
