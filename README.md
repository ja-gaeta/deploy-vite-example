# Github Pages

## Exemplo de Deploy de um Projeto Vite/React -

Passos para o Deploy de projeto react com vite:

- Se não estiver fazendo o deploy para `https://<USERNAME>.github.io/`, ajustar `base` no arquivo `vite.config.js` para o repositório. Ex.:

```
export default defineConfig({
  base: '/deploy-vite-example/', ⬅
  plugins: [reactRefresh()],
});
```

- Crie as páginas estáticas com o comando `npm run build`

- Adicione a pasta `dist` com a flag `-f`, pois ela está no `gitignore` e faça o `commit`:

```
git add dist -f
git commit -m "Adicionada pasta dist"
```

- Faça o `push` como uma nova branch com o nome `gh-pages`:

```
git subtree push --prefix dist origin gh-pages
```

O deploy está feito. Acesse `settings` no repositório onde encontrará o link para a página.
