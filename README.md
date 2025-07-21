# Estudo Completo de C# .Net Para Você
Nesse repositório você vai uma resumo completo de quase tudo o que você precisa saber e conhecer para ser um programador de C# .Net. Espero que gostem

// Curso Completo de C# com .NET - Por Thalison Jardim
------------

## ✅ Visão Geral
Este curso foi estruturado em módulos para facilitar o seu aprendizado em C# e .NET. Ele vai desde os fundamentos da linguagem até construção de APIs modernas com autenticação, versionamento e deploy profissional.

Cada módulo vem com explicações didáticas, exemplos práticos e boas práticas do mundo real.

Este repositório é um **guia definitivo** para levar seu conhecimento de C# (.NET) do zero ao nível **pleno** e além. Aqui você encontrará:

- **Conceitos fundamentais** e porquês de cada tecnologia.
- **Exemplos práticos** comentados passo a passo.
- **Padrões e práticas** de mercado (SOLID, DDD, CQRS).
- **Recursos avançados** (JWT, MediatR, Serilog, xUnit, Deployment).

Use este material para **estudar**, **referência** ou **avaliar seu nível**.
----------

## 📌 Visão Geral <a name="visão-geral"></a>
O objetivo deste projeto é apresentar **todas as camadas e tecnologias** que um desenvolvedor C# precisa dominar:
- **Linguagem e .NET**
- **Banco de dados e EF Core**
- **Arquitetura (DDD, CQRS)**
- **Segurança (JWT)**
- **Documentação (Swagger)**
- **Observabilidade (Serilog, testes)**
- **Deploy e operações**

Cada seção inclui uma **explicação teórica**, **racional** e **código comentado** para facilitar a compreensão.

---

## 🔄 Metodologia de Aprendizado <a name="metodologia"></a>
1. **Leitura e compreensão**: leia a explicação de cada tópico.
2. **Exploração do código**: analise os exemplos, entenda cada linha.
3. **Prática**: copie o trecho, execute localmente, faça alterações.
4. **Desafios extras**: implemente variações (ex: alterar lógica de negócio).
5. **Avaliação**: use o checklist de nível pleno para medir seu progresso.
6. **Revisão contínua**: revise tópicos em que identificar lacunas.



## 🧠 Conceitos Fundamentais de C#

### O que é C#?
C# é uma linguagem de programação orientada a objetos desenvolvida pela Microsoft. É usada principalmente com a plataforma .NET para criar aplicações web, desktop, mobile, APIs e muito mais.

### Principais conceitos de POO
| Conceito         | Definição e Porquê usar                                                | Exemplo Prático                                  |
|------------------|-------------------------------------------------------------------------|--------------------------------------------------|
| Encapsulamento   | Esconder detalhes internos e proteger estado                            | `private set;` em propriedades                   |
| Herança          | Reutilizar código comum em hierarquias                                  | `class Aluno : Pessoa { }`                       |
| Polimorfismo     | Tratar objetos de diferentes tipos de forma uniforme                    | `virtual` / `override` em métodos                |
| Abstração        | Representar conceitos do domínio sem revelar complexidade interna        | `interface IPagamento { void Pagar(); }`         |

```csharp
// Polimorfismo: múltiplos pagamentos
public interface IPagamento { void Pagar(); }
public class Pix : IPagamento { public void Pagar() => Console.WriteLine("Pagando via Pix"); }
public class Boleto : IPagamento { public void Pagar() => Console.WriteLine("Pagando via Boleto"); }
// Uso:
IPagamento p = new Pix(); p.Pagar();
```

```csharp
// Exemplo de Abstração
public abstract class Animal {
    public abstract void EmitirSom();
}

public class Cachorro : Animal {
    public override void EmitirSom() {
        Console.WriteLine("Latindo...");
    }
}
```


====================================
MÓDULO 1 - FUNDAMENTOS DO C#
====================================
- Tipos de dados (int, string, bool, etc.)
- Variáveis e constantes
- Operadores (aritméticos, lógicos, relacionais)
- Estruturas de decisão (if, else, switch)
- Estruturas de repetição (for, while, foreach)

```
// Aula 1: Hello World
using System;

class HelloWorld
{
    static void Main()
    {
        Console.WriteLine("Olá, Mundo!");
    }
}

// Aula 2: Tipos de Dados, Variáveis e Constantes
int idade = 28;
double salario = 3500.50;
bool ativo = true;
const double PI = 3.14;

// Aula 3: Operadores
int soma = 10 + 5;
bool maiorDeIdade = idade >= 18;

// Aula 4: Estruturas Condicionais
if (idade >= 18)
{
    Console.WriteLine("Maior de idade");
}
else
{
    Console.WriteLine("Menor de idade");
}

// Aula 5: Laços de Repetição
for (int i = 0; i < 5; i++)
{
    Console.WriteLine("Valor de i: " + i);
}

// Aula 6: Funções (Métodos)
static int Somar(int a, int b)
{
    return a + b;
}

```
====================================
MÓDULO 2 - ESTRUTURAS DE DADOS
====================================
- Tipos primitivos: int, string, bool, float, double, decimal
- Operadores: +, -, *, /, %, ==, !=, >, <, >=, <=, &&, ||
- Conversões de tipo (casting)

```csharp
int idade = 25;
double salario = 2500.50;
string nome = "João";
bool ativo = true;


// Arrays
int[] numeros = new int[] { 1, 2, 3, 4, 5 };

// Listas
using System.Collections.Generic;
List<string> nomes = new List<string> { "Ana", "João", "Lucas" };
nomes.Add("Maria");

```
====================================
MÓDULO 3 - ORIENTAÇÃO A OBJETOS
====================================
- Classes e objetos
- Encapsulamento
- Herança
- Polimorfismo
- Interfaces

```
class Pessoa
{
    public string Nome;
    public int Idade;

    public void Apresentar()
    {
        Console.WriteLine($"Meu nome é {Nome} e tenho {Idade} anos.");
    }
}

// Instanciando um objeto
Pessoa p = new Pessoa();
p.Nome = "Thalison";
p.Idade = 29;
p.Apresentar();

```
====================================
MÓDULO 4 - MANIPULAÇÃO DE ARQUIVOS
====================================
```
using System.IO;

File.WriteAllText("dados.txt", "Conteúdo do arquivo");
string conteudo = File.ReadAllText("dados.txt");
Console.WriteLine(conteudo);

```
====================================
MÓDULO 5 - LINQ E COLEÇÕES
====================================
- List, Dictionary, HashSet
- LINQ (Where, Select, FirstOrDefault, etc.)

```csharp
var nomes = new List<string> { "Ana", "Bruno", "Carlos" };
var encontrados = nomes.Where(n => n.StartsWith("B"))


using System.Linq;

var maiores = numeros.Where(n => n > 2).ToList();

```
====================================
MÓDULO 6 - ASP.NET BÁSICO
====================================
// Crie um projeto com: dotnet new webapi
// A estrutura básica será:
// - Controllers
// - Models
// - Services

// Exemplo de Controller
```
[ApiController]
[Route("api/[controller]")]
public class ProdutosController : ControllerBase
{
    [HttpGet]
    public IActionResult Get() => Ok(new[] { "Produto 1", "Produto 2" });
}
```
====================================
MÓDULO 7 - API REST COM .NET
====================================
// - Uso do Entity Framework
// - Endpoints REST (GET, POST, PUT, DELETE)
// - Criação de Models e Contexto do Banco

```bash
dotnet new webapi -n MinhaApi
```
- Estrutura padrão criada
- Configuração do appsettings.json
- Configuração do `Program.cs


/*
====================================
MÓDULO 8 - ENTITY FRAMEWORK
====================================


### Modelo Produto
```csharp
public class Produto
{
    public int Id { get; set; }
    public string Nome { get; set; }
    public decimal Preco { get; set; }
    public int Estoque { get; set; }
}
```
*/
// Exemplo de model EF
/*
public class Produto
{
    public int Id { get; set; }
    public string Nome { get; set; }
    public decimal Preco { get; set; }
}

public class AppDbContext : DbContext
{
    public DbSet<Produto> Produtos { get; set; }
}
*/

// Crie o contexto e use "dotnet ef migrations add Inicial" e "dotnet ef database update"

/*

### AppDbContext
```csharp
using Microsoft.EntityFrameworkCore;

public class AppDbContext : DbContext
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options) {}
    public DbSet<Produto> Produtos { get; set; }
}
```

### ProdutosController
```csharp
[ApiController]
[Route("api/[controller]")]
public class ProdutosController : ControllerBase
{
    private readonly AppDbContext _context;
    public ProdutosController(AppDbContext context)
    {
        _context = context;
    }

    [HttpGet]
    public async Task<ActionResult<List<Produto>>> Get() => await _context.Produtos.ToListAsync();

    [HttpGet("{id}")]
    public async Task<ActionResult<Produto>> Get(int id)
    {
        var produto = await _context.Produtos.FindAsync(id);
        return produto is null ? NotFound() : produto;
    }

    [HttpPost]
    public async Task<ActionResult> Post(Produto produto)
    {
        _context.Produtos.Add(produto);
        await _context.SaveChangesAsync();
        return CreatedAtAction(nameof(Get), new { id = produto.Id }, produto);
    }

    [HttpPut("{id}")]
    public async Task<IActionResult> Put(int id, Produto produto)
    {
        if (id != produto.Id) return BadRequest();
        _context.Entry(produto).State = EntityState.Modified;
        await _context.SaveChangesAsync();
        return NoContent();
    }

    [HttpDelete("{id}")]
    public async Task<IActionResult> Delete(int id)
    {
        var produto = await _context.Produtos.FindAsync(id);
        if (produto is null) return NotFound();
        _context.Produtos.Remove(produto);
        await _context.SaveChangesAsync();
        return NoContent();
    }
}
```

### Comandos EF Core
```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
```

---


====================================
 EXERCÍCIOS E PROJETOS
====================================

// Sugestão de projetos:
// - CRUD de produtos
// - API de tarefas
// - Sistema de login
// - Calculadora console
// - Manipulação de arquivos com log


## 🏗️ Estrutura com DDD (Domain Driven Design)

```
📁 Domain
  └── Entidades, Interfaces, Agregados
📁 Application
  └── Casos de Uso (Services), DTOs
📁 Infrastructure
  └── Repositórios, EF, Configuração
📁 WebAPI
  └── Controllers, Program.cs, Middlewares
```

### Exemplo de divisão:
- `Cliente` → entidade no Domain
- `CriarClienteService` → Application
- `ClienteRepository` → Infrastructure
- `ClienteController` → WebAPI

  ## MÓDULO: CRUD com Entity Framework

### Modelo Produto
```csharp
public class Produto
{
    public int Id { get; set; }
    public string Nome { get; set; }
    public decimal Preco { get; set; }
    public int Estoque { get; set; }
}
```


## 🔐 Autenticação com JWT + Refresh Token

### Por que usar?
JWT permite autenticar APIs de forma segura e stateless.

### Passos:
1. Gerar Token JWT
2. Armazenar Refresh Token
3. Renovar com endpoint /refresh

```csharp
// Gerar Token
var token = new JwtSecurityToken(...);
return new JwtSecurityTokenHandler().WriteToken(token);
```

## Autenticação com JWT

### 1. Criar classe de usuário e login
```csharp
public class Usuario
{
    public string Username { get; set; }
    public string Password { get; set; }
}

public class LoginRequest
{
    public string Username { get; set; }
    public string Password { get; set; }
}
```

### 2. Gerar Token
```csharp
using Microsoft.IdentityModel.Tokens;
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Text;

public static class TokenService
{
    public static string GerarToken(Usuario usuario)
    {
        var key = Encoding.ASCII.GetBytes("chave-super-secreta-1234");

        var tokenDescriptor = new SecurityTokenDescriptor
        {
            Subject = new ClaimsIdentity(new[]
            {
                new Claim(ClaimTypes.Name, usuario.Username)
            }),
            Expires = DateTime.UtcNow.AddHours(1),
            SigningCredentials = new SigningCredentials(new SymmetricSecurityKey(key), SecurityAlgorithms.HmacSha256Signature)
        };

        var tokenHandler = new JwtSecurityTokenHandler();
        var token = tokenHandler.CreateToken(tokenDescriptor);

        return tokenHandler.WriteToken(token);
    }
}
```

### 3. LoginController
```csharp
[ApiController]
[Route("api/[controller]")]
public class LoginController : ControllerBase
{
    [HttpPost]
    public IActionResult Login(LoginRequest request)
    {
        // Exemplo simples (depois conectar com banco)
        if (request.Username == "admin" && request.Password == "1234")
        {
            var token = TokenService.GerarToken(new Usuario { Username = request.Username });
            return Ok(new { token });
        }

        return Unauthorized();
    }
}
```

### 4. Configurar JWT no Program.cs
```csharp
builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options =>
    {
        options.TokenValidationParameters = new TokenValidationParameters
        {
            ValidateIssuerSigningKey = true,
            IssuerSigningKey = new SymmetricSecurityKey(Encoding.ASCII.GetBytes("chave-super-secreta-1234")),
            ValidateIssuer = false,
            ValidateAudience = false
        };
    });

app.UseAuthentication();
app.UseAuthorization();
```



## 🪄 Injeção de Dependência Avançada

### O que é?
Permite inverter o controle de dependências (Inversão de Controle)

```csharp
services.AddScoped<IClienteRepository, ClienteRepository>();
services.AddScoped<CriarClienteService>();
```

## 📘 CQRS + Mediator com MediatR

### Por que usar?
Separa comandos (escrita) de queries (leitura), facilitando manutenção

```csharp
// Command
public record CriarClienteCommand(string Nome) : IRequest<bool>;

// Handler
public class CriarClienteHandler : IRequestHandler<CriarClienteCommand, bool> {
  public Task<bool> Handle(CriarClienteCommand cmd, CancellationToken ct) {
    // lógica aqui
  }
}
```

## 🧪 Testes Automatizados com xUnit

```csharp
public class ClienteTests {
  [Fact]
  public void DeveCriarClienteComNomeValido() {
    var cliente = new Cliente("João");
    Assert.Equal("João", cliente.Nome);
  }
}
```

## 🧾 Swagger + Versionamento de API

```csharp
// Swagger no Program.cs
builder.Services.AddSwaggerGen(c => {
  c.SwaggerDoc("v1", new OpenApiInfo { Title = "Minha API", Version = "v1" });
});

// Versionamento
services.AddApiVersioning(options => {
  options.DefaultApiVersion = new ApiVersion(1, 0);
  options.AssumeDefaultVersionWhenUnspecified = true;
  options.ReportApiVersions = true;
});
```

## 📊 Logging com Serilog

```csharp
Log.Logger = new LoggerConfiguration()
    .WriteTo.Console()
    .WriteTo.File("logs/api.log")
    .CreateLogger();
```

## ☁️ Deploy no Azure App Service

### Passos:
1. Criar App Service no Azure
2. Publicar pelo Visual Studio ou CLI
3. Configurar ambiente

## 🚂 Deploy no Railway

### Passos:
1. Criar projeto no Railway
2. Conectar ao GitHub
3. Inserir variáveis de ambiente (Connection String, etc)

## ✅ O que o programador C# não pode esquecer:

- `using System.Linq` para consultas
- `async/await` para métodos assíncronos
- `IDisposable` para liberar recursos
- Validação com `FluentValidation`
- `Automapper` para mapear DTOs

## 🚫 Certo x Errado

### Errado
```csharp
public void CriarCliente(string nome) {
  var cliente = new Cliente();
  cliente.Nome = nome;
  _db.Clientes.Add(cliente);
  _db.SaveChanges();
}
```

### Certo
```csharp
public class CriarClienteService {
  public void Executar(string nome) {
    var cliente = new Cliente(nome);
    _repo.Adicionar(cliente);
  }
}
```
## 🏗 Estrutura de Projeto (DDD) <a name="estrutura-de-projeto"></a>
**Domain-Driven Design** separa responsabilidades:

```
src/
├── Domain        # Entidades, Value Objects, Exceções, Interfaces
├── Application   # Serviços, Cases de uso, DTOs, Handlers
├── Infrastructure # EF Core, Repositórios, Migrations, Config
└── API           # Controllers, Middlewares, Program.cs
```  
**Por quê?** Facilita manutenção, teste e evolução independente de infraestrutura.

---

## 📦 CRUD Básico com EF Core <a name="crud-basico"></a>
1. **Model**: define dados
```csharp
public class Produto {
  public int Id { get; set; }
  public string Nome { get; set; }
  public decimal Preco { get; set; }
  public int Estoque { get; set; }
}
```
2. **DbContext**: mapeia entidades
```csharp
public class AppDbContext : DbContext {
  public DbSet<Produto> Produtos { get; set; }
}
```
3. **Repository**: abstrai acesso a dados
```csharp
public interface IProdutoRepository {
  Task<List<Produto>> GetAllAsync();
  Task<Produto> GetByIdAsync(int id);
  Task AddAsync(Produto p);
  // ...
}
```
4. **Service**: lógica de negócio
```csharp
public class ProdutoService {
  public async Task AdicionarAsync(Produto p) {
    if (p.Preco < 0) throw new DomainException("Preço inválido");
    await _repo.AddAsync(p);
  }
}
```
5. **Controller**: expõe API
```csharp
[HttpPost]
public async Task<IActionResult> Post([FromBody]Produto p) {
  await _service.AdicionarAsync(p);
  return CreatedAtAction(...);
}
```

**Prática**: tente alterar para atualização e exclusão, valide entradas e use DTOs.

---

## 🔐 Autenticação JWT + Refresh Token <a name="jwt-refresh"></a>
**Por quê?** Autenticação stateless, escalável, sem sessão no servidor.

1. **Gerar JWT**  
```csharp
var tokenHandler = new JwtSecurityTokenHandler();
var token = tokenHandler.CreateToken(descriptor);
return tokenHandler.WriteToken(token);
```
2. **Refresh Token**: gera token longo e armazena no banco
3. **Endpoint /refresh**: valida refresh e emite novo JWT

**Exemplo**: implemente classes `AuthController`, `LoginRequest`, `RefreshRequest` com validações e comentários.

---

## ⚡ CQRS + MediatR <a name="cqrs-mediatr"></a>
**Por quê?** Separar leitura e escrita melhora performance e manutenibilidade.

- **Command** (escrita)
```csharp
public record CreateOrderCommand(int CustomerId) : IRequest<int>;
```
- **Query** (leitura)
```csharp
public record GetOrderByIdQuery(int Id) : IRequest<OrderDto>;
```
- **Handler**: processa command/query
```csharp
public class CreateOrderHandler : IRequestHandler<CreateOrderCommand,int> { ... }
```

**Prática**: crie query e command para `Produto` e teste usando MediatR.

---

## 🧾 Swagger e Versionamento <a name="swagger-versionamento"></a>
**Swagger** gera documentação interativa.
```csharp
services.AddSwaggerGen(c => {
  c.SwaggerDoc("v1", new() { Title="API", Version="v1" });
});
```
**Versionamento**
```csharp
services.AddApiVersioning(o=>{o.DefaultApiVersion=new(1,0);o.ReportApiVersions=true;});
```
Use namespaces ou rotas `/api/v{version}/...`.

---

## 🔍 Logging com Serilog <a name="logging-serilog"></a>
**Por quê?** Logs estruturados facilitam diagnóstico e monitoramento.
```csharp
Log.Logger = new LoggerConfiguration()
  .WriteTo.Console()
  .WriteTo.File("logs/log-.txt",rollingInterval:Day)
  .CreateLogger();
host.UseSerilog();
```
**Prática**: injete `ILogger<T>` em Controllers e Services.

---

## 🧪 Testes Automatizados com xUnit <a name="testes-xunit"></a>
**Por quê?** Garante qualidade e previne regressões.
```csharp
[Fact]
public async Task AddProduct_Should_Persist() {
  var repo = new InMemoryProdutoRepository();
  await repo.AddAsync(new Produto(...));
  var list = await repo.GetAllAsync();
  Assert.Single(list);
}
```
Crie testes unitários e de integração (InMemoryDb).

---

## 🚀 Deploy (Azure & Railway) <a name="deploy"></a>
**Azure**
1. Criar App Service  
2. Configurar connection string  
3. Publicar via VS/CLI `dotnet publish`

**Railway**
1. Conectar GitHub  
2. Configurar variáveis (`DOTNET_ENVIRONMENT`,`Jwt__Key`,`ConnectionStrings__Default`)  
3. Deploy automático a cada push

---

## 🧰 Conceitos Básicos que você precisa saber:

- Tipos de dados: `int`, `string`, `bool`
- Nullable Types: `int?`, `DateTime?`
- Linq: `Where`, `Select`, `FirstOrDefault`
- Exceptions: `try`, `catch`, `throw`
- Collections: `List<T>`, `Dictionary<K,V>`
- JSON: `System.Text.Json` ou `Newtonsoft.Json`

## FUNÇÕES E CONCEITOS ESSENCIAIS QUE VOCÊ NÃO PODE ESQUECER:

### Métodos mais usados:
- `.ToListAsync()` → converte para lista
- `.FindAsync(id)` → busca por chave primária
- `.Where()` e `.Select()` do LINQ
- `ModelState.IsValid` → valida modelo no POST

### Boas práticas:
- Separe responsabilidades (Controller, Service, Repository)
- Use DTOs para retorno e entrada de dados
- Não exponha diretamente entidades do EF

### Dicas gerais para programador C#:
- Sempre configure logs (ex: `ILogger<T>`)
- Use `async/await` sempre que possível
- Prefira `IEnumerable<>` para leitura e `IQueryable<>` em consultas LINQ
- Organize seu projeto em camadas (Presentation, Application, Domain, Infra)

## 💡 Dicas e Práticas Avançadas <a name="dicas-avancadas"></a>
- **SOLID** e **Clean Code**: métodos pequenos, nomes claros.  
- Use **AutoMapper** para mapear DTOs.  
- **FluentValidation** para validações complexas.  
- **Middleware** para tratamento global de erros.  
- **Async/Await** em todas chamadas I/O.  
- **Rate Limiting**, **Caching** e **Health Checks** (AspNetCore.HealthChecks).  

---

## ✔️ Checklist de Nível Pleno <a name="checklist-pleno"></a>
- [ ] Entende e aplica POO e SOLID
- [ ] Implementa DDD básico com camadas separadas
- [ ] Cria APIs REST com versionamento
- [ ] Usa JWT + Refresh Token corretamente
- [ ] Documenta com Swagger
- [ ] Registra logs com Serilog
- [ ] Escreve testes unitários e de integração
- [ ] Configura e efetua deploy automático
- [ ] Aplica CQRS com MediatR
- [ ] Usa AutoMapper e FluentValidation

---

---




