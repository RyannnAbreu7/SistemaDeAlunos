class Aluno:
    def __init__(self, nome="Não definido", idade=0, curso="Não definido", numero_matricula="0000"):
        self.nome = nome
        self.idade = idade
        self.curso = curso
        self.numero_matricula = numero_matricula

    def exibir_informacoes(self):
        print("\n--- Informações do Aluno ---")
        print(f"Nome: {self.nome}")
        print(f"Idade: {self.idade}")
        print(f"Curso: {self.curso}")
        print(f"Número de Matrícula: {self.numero_matricula}")
        print("----------------------------")


def main():
    lista_alunos = []

    while True:
        print("\n=== Sistema de Registro de Alunos ===")
        print("1. Criar novo aluno")
        print("2. Exibir informações dos alunos")
        print("3. Sair")
        opcao = input("Escolha uma opção: ")

        if opcao == '1':
            nome = input("Nome: ")
            while True:
                try:
                    idade = int(input("Idade: "))
                    break
                except ValueError:
                    print("Idade inválida. Tente novamente.")
            curso = input("Curso: ")
            numero_matricula = input("Número de Matrícula: ")
            aluno = Aluno(nome, idade, curso, numero_matricula)
            lista_alunos.append(aluno)
            print("Aluno registrado com sucesso!")

        elif opcao == '2':
            if not lista_alunos:
                print("Nenhum aluno registrado.")
            else:
                for i, aluno in enumerate(lista_alunos, start=1):
                    print(f"\nAluno {i}:")
                    aluno.exibir_informacoes()

        elif opcao == '3':
            print("Encerrando o sistema. Até logo!")
            break

        else:
            print("Opção inválida. Tente novamente.")


if __name__ == "__main__":
    main()
