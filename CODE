import openai
import os

def gerar_texto(prompt, modelo="gpt-4", max_tokens=500):
    """
    Função para gerar um texto utilizando a API da OpenAI.
    """
    try:
        response = openai.ChatCompletion.create(
            model=modelo,
            messages=[{"role": "user", "content": prompt}],
            max_tokens=max_tokens
        )
        return response["choices"][0]["message"]["content"].strip()
    except Exception as e:
        return f"Erro ao gerar texto: {str(e)}"

def main():
    """
    Função principal para interagir com o usuário e gerar texto.
    """
    openai.api_key = os.getenv("OPENAI_API_KEY")  # Defina sua chave de API como variável de ambiente
    
    print("\n🔹 Gerador de Textos com IA 🔹\n")
    tema = input("Digite um tema para o texto: ")
    prompt = f"Escreva um texto detalhado sobre {tema}."
    
    texto_gerado = gerar_texto(prompt)
    
    print("\n📝 Texto Gerado:\n")
    print(texto_gerado)
    
    salvar = input("\nDeseja salvar o texto? (s/n): ")
    if salvar.lower() == 's':
        with open("texto_gerado.txt", "w", encoding="utf-8") as arquivo:
            arquivo.write(texto_gerado)
        print("Texto salvo como 'texto_gerado.txt'!")
    
if __name__ == "__main__":
    main()

