# DjangoWeb2

Projeto em django para cadastrar dados no banco mysql e posteriormente buscar as informa��es para exibir na web.

# Funcionalidades

- [ ] Cadastro de usuario e produto atraves da area administrativa do django.
- [ ] Rotas para navega��o entre index, produto, contato.
- [ ] Pagina para informar erro no servidor (404, 500).
- [ ] Arquivos estaticos para css, js e imagem.

## Pacotes utilizados

```bash
asgiref
autopep8
Django
gunicorn
pycodestyle
pytz
sqlparse
toml
whitenoise
```

Use o gerenciador de pacotes [pip](https://pypi.org/) para instala��o, exemplo:

```bash
pip install Django gunicorn whitenoise
```

## Uso do models no django

```python
from django.db import models

class Produto(models.Model):
    nome = models.CharField('Nome', max_length=100)
    preco = models.DecimalField('Pre�o', decimal_places=2, max_digits=8)
    estoque = models.IntegerField('Quantidade em Estoque')
```
