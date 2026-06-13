# Sistema-de-Gerenciamento-Escolar
# ============================================================
#  Sistema de Gerenciamento Escolar (SGE)
#  Disciplina: Algoritmos e Logica de Programacao
#  Atividade Pratica - Modulo de Fechamento de Notas
# ============================================================

def ler_nota(nome_avaliacao):
    """Le e valida uma nota entre 0 e 10."""
    while True:
        try:
            nota = float(input(f"  Digite a nota de {nome_avaliacao}: "))
            if 0 <= nota <= 10:
                return nota
            else:
                print("  [ERRO] Nota invalida! Insira valor entre 0.0 e 10.0.")
        except ValueError:
            print("  [ERRO] Entrada invalida! Digite um numero.")


def calcular_media(p1, p2, pd, pp1, pp2, pp3):
    """Calcula a media aritmetica das 6 avaliacoes."""
    return (p1 + p2 + pd + pp1 + pp2 + pp3) / 6


def verificar_situacao(media):
    if media >= 6.0:
        return "Aluno Aprovado"
    elif media >= 4.0:
        return "Aluno em Recuperacao"
    else:
        return "Aluno Reprovado"


def main():
    print("=" * 50)
    print("   SISTEMA DE GERENCIAMENTO ESCOLAR (SGE)")
    print("=" * 50)
    print("\n[MENU PRINCIPAL - DADOS DO ALUNO]")
    nome_aluno = input("  Nome do Aluno   : ").strip()
    cod_disc   = input("  Cod. Disciplina : ").strip()
    print("\n[LANCAMENTO DE NOTAS]")
    p1  = ler_nota("P1")
    p2  = ler_nota("P2")
    pd  = ler_nota("PD")
    pp1 = ler_nota("Pp1")
    pp2 = ler_nota("Pp2")
    pp3 = ler_nota("Pp3")
    media_final = calcular_media(p1, p2, pd, pp1, pp2, pp3)
    situacao    = verificar_situacao(media_final)
    print("\n" + "=" * 50)
    print("   RELATORIO FINAL")
    print("=" * 50)
    print(f"  Aluno      : {nome_aluno}")
    print(f"  Disciplina : {cod_disc}")
    print(f"  Media Final: {media_final:.2f}")
    print(f"  Situacao   : {situacao}")
    print("=" * 50)

if __name__ == "__main__":
    main()
