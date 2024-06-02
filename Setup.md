## Generate `.gitignore` for C++ and CMake
```sh
cat > .gitignore << EOF
$(curl -s "https://raw.githubusercontent.com/github/gitignore/main/C%2B%2B.gitignore")

# Clangd
.cache

# Bazel
$(curl -s "https://raw.githubusercontent.com/github/gitignore/main/community/Bazel.gitignore")
EOF
```

## Install C++ build tools
```sh
brew install bazelisk buildifier
bazel --version | grep -oE "([0-9]+\.){2}[0-9]+" > .bazelversion
# TODO: set up MODULE.bazel
bazel build //sv:factorial
bazel run @hedron_compile_commands//:refresh_all
bazel test sv:factorial-test

# git restore --source cmake-conan sv/factorial.cc
bazel clean --expunge
```
