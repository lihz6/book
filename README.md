```bash
# git submodule add --depth=1 -- https://github.com/rust-lang-nursery/mdBook mdBook

git submodule update

cd mdBook && cargo build && cd ..

for book in rust-*; do
  ./mdBook/target/debug/mdbook build $book --dest-dir ../docs/$book
done

git add .
git commit -m $(date +'%Y-%m-%d')
git push
```
