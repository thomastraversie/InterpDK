# Interpretation of theories in Dedukti

[Dedukti](https://github.com/Deducteam/Dedukti) is a proof language based on the λΠ-calculus modulo theory, that is λ-calculus with dependent types and user-defined rewrite rules. This repository presents a Dedukti formalization of the interpretation of theories of the λΠ-calculus modulo theory. The interpretation uses two translation, such that the translations of the term `t` are written `t_s` and `t_p`. 

- `lo.dk` contains the prelude encoding of the notions of proposition and proof.

- `lo_sp.dk` contains the parameters for interpreting the prelude encoding.

In particular, we check in `lo_sp.dk` that, for each rewrite rule `l --> r` of the prelude encoding, `l_s` and `r_s` are convertible and `l_p` and `r_p` are convertible.


## Example

We illustrate the interpretation of theories thanks to a theory representing natural numbers and a theory representing integers. We provide the parameters for interpreting the theory of natural numbers in the theory of integers, and we show how to transnport theorems for free from `nat.dk` to `int.dk`.

- `nat.dk` specifies a theory of natural numbers.

- `int.dk` specifies a theory of integers.

- `nat_sp.dk` contains the parameters for interpreting `nat.dk` in `int.dk`. It does not depend on the constants of `nat.dk`, but on the constants of `int.dk`. The two theorems of `nat.dk` are derived in `nat_sp.dk` using the translations.



## How to use it?

- Install [Dedukti](https://github.com/Deducteam/Dedukti?tab=readme-ov-file#install-with-opam).

- Clone and enter this repository.
```
git clone https://github.com/thomastraversie/InterDK/
cd InterpDK
```

- Typecheck the files. Do not forget to generate the objects files `.dko`. 
```
dk check -e lo.dk lo_sp.dk int.dk 
dk check nat.dk 
dk check nat_sp.dk
```


