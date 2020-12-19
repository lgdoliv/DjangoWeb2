# DjangoWeb2

Projeto django para cadastro e consulta de dados atraves do banco mysql, visualização de imagens armanezadas e envio de formulario.

# Funcionalidades

- [x] Cadastro de usuario e produto atraves da area administrativa do django.
- [x] Rotas para navegação entre index, produto, contato e media
- [x] Envio de formulário atraves da pagina contato.

## Pacotes Principais

```bash
dj-database-url
dj-static
Django
django-bootstrap4
django-stdimage
gunicorn
mysqlclient @ file:///C:/Django2/mysqlclient-1.4.6-cp37-cp37m-win32.whl
psycopg2-binary
pycodestyle
python-utils
```

Use o gerenciador de pacotes [pip](https://pypi.org/) para instalação, exemplo:

```bash
pip install Django django-bootstrap4 django-stdimage gunicorn
```
## Client MySql

Caso a instalação via pip apresente erro, o pacote binario pode ser instalado com os comandos:
```bash
pip install wheel
pip install mysqlclient-1.4.6-cp37-cp37m-win32.whl
```
Existem outras versões do client disponiveis no [LFD](https://www.lfd.uci.edu/~gohlke/pythonlibs/#mysqlclient)

## Uso do ContatoForm no django

```python
from core.forms import ContatoForm

def contato(request):
    form = ContatoForm(request.POST or None)
    if str(request.method) == 'POST':
        if form.is_valid():
            form.send_mail()
            messages.success(request, 'Email enviado com sucesso!')
            form = ContatoForm()
        else:
            messages.error(request, 'Erro ao enviar email')

    context = {'form': form}
    return render(request, 'contato.html', context)
```
