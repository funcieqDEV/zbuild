# ZBuild

A self-hosted build tool for the [Zap programming language](https://github.com/thezaplang/zap).

## Requirements

- [Zap](https://github.com/thezaplang/zap) `v0.1.1`

## Building from Source

Zbuild is self-hosted — it uses itself to build itself. The first build must be done manually using the Zap compiler directly.

### Step 1 — Bootstrap

```bash
git clone https://github.com/funcieqDEV/zbuild
cd zbuild
mkdir -p build
zapc src/main.zp -o build/zbuild
```

### Step 2 — Self-hosted build

Once the bootstrap binary exists, use it to rebuild Zbuild with Zbuild itself:

```bash
./build/zbuild build
```

You now have a fully self-hosted Zbuild binary.

## Adding to PATH

```bash
# Option A — copy to a directory already in PATH
sudo cp build/zbuild /usr/local/bin/zbuild

# Option B — add the build directory to PATH (add to ~/.bashrc or ~/.zshrc)
export PATH="$PATH:/path/to/zbuild/build"
source ~/.bashrc
```

Verify:

```bash
zbuild --version
```

## Usage

```bash
zbuild build
```

## License

See [LICENSE](LICENSE).
