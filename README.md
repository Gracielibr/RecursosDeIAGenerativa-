# RecursosDeIAGenerativa-

# Desafio DIO: Explorando Copiloto e OpenAI com Java

## Descrição do Projeto
Este repositório documenta minha experiência no desafio de explorar as funcionalidades do Copiloto e ferramentas da OpenAI, com foco na aplicação desses conceitos usando Java e compartilhando os resultados no GitHub.

## Objetivos Alcançados
- [x] Aplicação dos conceitos aprendidos em ambiente prático com Java
- [x] Documentação clara e estruturada dos processos técnicos
- [x] Utilização do GitHub para compartilhamento de documentação técnica

## Estrutura do Repositório
```
/
├── src/                 # Códigos fonte Java
│   ├── Main.java        # Exemplo principal
│   └── OpenAIDemo.java  # Demonstração de integração
├── images/              # Capturas de tela relevantes
├── docs/                # Documentação adicional
└── README.md            # Este arquivo
```

## Exemplo de Código Java
```java
// src/OpenAIDemo.java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;

public class OpenAIDemo {
    public static void main(String[] args) {
        String apiKey = "sua-chave-api";
        String endpoint = "https://api.openai.com/v1/completions";
        
        String requestBody = """
        {
            "model": "text-davinci-003",
            "prompt": "Explique inteligência artificial em termos simples",
            "max_tokens": 100,
            "temperature": 0.7
        }
        """;
        
        HttpClient client = HttpClient.newHttpClient();
        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create(endpoint))
                .header("Content-Type", "application/json")
                .header("Authorization", "Bearer " + apiKey)
                .POST(HttpRequest.BodyPublishers.ofString(requestBody))
                .build();
        
        try {
            HttpResponse<String> response = client.send(request, 
                HttpResponse.BodyHandlers.ofString());
            System.out.println("Resposta da OpenAI:\n" + response.body());
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Aprendizados
1. **Integração com OpenAI**: Como conectar aplicações Java à API da OpenAI
2. **Filtros de Conteúdo**: Implementação de mecanismos para garantir saídas apropriadas
3. **GitHub Markdown**: Formatação eficaz de documentação técnica
4. **Copiloto**: Utilização de IA assistida para desenvolvimento de código

## Recursos Utilizados
- [Documentação OpenAI](https://platform.openai.com/docs)
- [Java HTTP Client](https://docs.oracle.com/en/java/javase/11/docs/api/java.net.http/java/net/http/HttpClient.html)
- [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/)

## Como Contribuir
1. Faça um fork do repositório
2. Crie uma branch com sua feature (`git checkout -b feature/awesome-feature`)
3. Commit suas mudanças (`git commit -m 'Add some awesome feature'`)
4. Push para a branch (`git push origin feature/awesome-feature`)
5. Abra um Pull Request

## Licença
Este projeto está licenciado sob a MIT License - veja o arquivo [LICENSE](LICENSE) para detalhes.
