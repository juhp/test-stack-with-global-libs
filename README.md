# test-stack-with-global-libs

For testing https://github.com/commercialhaskell/stack/issues/6661

The problem should be reproducible a fedora:43 container:

```
# dnf install ghc stack git-core ghc-attoparsec-aeson-devel
:
:
# git clone this/repo
# cd here
# stack build
```

Though I have been using a Fedora toolbox container to share
my homedir and avoid recreating all of `~/.stack`.

This results in the error:

```
attoparsec-aeson           > configure
attoparsec-aeson           > Configuring attoparsec-aeson-2.2.2.0...
attoparsec-aeson           > Error: Cabal-simple_CKvAmRb3_3.10.3.0_ghc-9.8.4: Encountered missing or
attoparsec-aeson           > private dependencies:
attoparsec-aeson           > attoparsec ==0.14.4
attoparsec-aeson           >
```
