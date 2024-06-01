## Generate `.gitignore` for C++ and CMake
```sh
cat > .gitignore << EOF
$(curl -s "https://raw.githubusercontent.com/github/gitignore/main/C%2B%2B.gitignore")

# Clangd
.cache
EOF
```
