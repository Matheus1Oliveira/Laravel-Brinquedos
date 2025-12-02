# laravel-ecommerce

Repositório adaptado por `Matheus1Oliveira` a partir do tutorial "Laravel 12 Simple E-commerce Application" (tema: brinquedos).

> **Resumo:** projeto Laravel pronto para rodar localmente. Este README traz os passos mínimos para configurar o projeto após clonar — comandos, dependências e dicas de resolução de problemas.

---

## Pré-requisitos

* PHP 8.1+ (ou versão compatível com Laravel 12)
* Composer
* Node.js + npm
* MySQL ou outro banco suportado (e criar database)
* Git

---

## Passos rápidos (comandos que você deve executar assim que clonar)

> Execute estes comandos na raiz do repositório, em um terminal.

1. Clonar o repositório

```bash
https://github.com/Matheus1Oliveira/Laravel-Brinquedos.git
cd laravel-ecommerce
```

2. Instalar dependências PHP

```bash
# se você NÃO possui a pasta vendor (gitignore), rode:
composer install
```

3. gerar APP_KEY

```bash
php artisan key:generate
```

4. Verificar `.env`

* Edite `.env` e configure as variáveis do banco de dados (`DB_DATABASE`, `DB_USERNAME`, `DB_PASSWORD`) e `APP_URL` se necessário.

5. Instalar dependências de front-end

```bash
npm install
# e compilar assets (modo dev):
npm run dev
```

6. Migrar banco e popular

```bash
php artisan migrate
# se houver seeders:
php artisan db:seed
```

7. Rodar servidor local

```bash
php artisan serve
# acessa em http://127.0.0.1:8000
```

---

## Comandos úteis para desenvolvimento / troubleshooting

* Limpar caches:

```bash
php artisan route:clear
php artisan config:clear
php artisan cache:clear
php artisan view:clear
php artisan optimize:clear
```

* Regenerar autoload/composer dump:

```bash
composer dump-autoload
```

* Se aparecer `403` ou imagens não carregarem:

  * Certifique-se que `storage:link` foi executado e que o diretório `storage/app/public` contém as imagens.
  * Verifique permissões de `storage` e `bootstrap/cache`.

---

## Como definir sua página inicial (root) — visão geral

A rota raiz (`/`) é definida em `routes/web.php`. Se o `php artisan serve` abrir a `welcome.blade.php` e você quer que abra outra view (por exemplo `brinquedos.index` ou uma página `home` sua), altere a rota raiz para apontar para sua controller ou view.

Exemplos e instruções mais detalhadas estão disponíveis nesta documentação do repositório.

---

## Estrutura importante (onde procurar o que editar)

* `routes/web.php` — rotas públicas (onde está a rota `/`)
* `app/Http/Controllers` — controllers (ex.: HomeController, ProductController)
* `resources/views` — views Blade (a `welcome.blade.php` está aqui)
* `public` — arquivos públicos (assets)

---

## Observações

* `vendor/` e `node_modules/` geralmente estão no `.gitignore` — por isso o `composer install` e `npm install` são necessários após clonar.
* Se você usa outro SGBD, ajuste o `.env` e os drivers conforme necessário.

---

## Licença

MIT

---
