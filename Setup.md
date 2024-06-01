## Generate `.gitignore` for C++ and CMake
```sh
cat > .gitignore << EOF
$(curl -s "https://raw.githubusercontent.com/github/gitignore/main/C%2B%2B.gitignore")

# Clangd
.cache

# CMake
$(curl -s "https://raw.githubusercontent.com/github/gitignore/main/CMake.gitignore")
EOF
```

## Install C++ build tools
```sh
pip3 install cmake conan ninja
conan install . --profile conanprofile --build missing
```
