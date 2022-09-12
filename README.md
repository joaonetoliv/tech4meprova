# tech4meprova
PROVA TECH4ME JOÃO NETO -  Programação orientada a objetos

package aplicativos;

import java.io.IOException;
import java.util.Scanner;

public class AppPilotos {
    public static void main(String[] args) throws InterruptedException, IOException {
        final int MAX_ELEMENTOS = 20;
        int opcao, qtdCadastrados = 0;
        Pessoa[] pilotos = new Pessoa[MAX_ELEMENTOS];
        Scanner in = new Scanner(System.in);
        int novoElemento, novoArmazenamento, maximoElemento; 

        do {
            System.out.println("\n****\nMENU\n****\n");
            System.out.println("1 - Cadastrar piloto");
            System.out.println("2 - Listar pilotos cadastrados");
            System.out.println("3 - Localizar piloto pelo CPF");
            System.out.println("4 - Aumentar espaço de armazenamento");
            System.out.println("0 - Sair");
            System.out.print("Opção: ");

            opcao = in.nextInt();
            in.nextLine(); // Tira o ENTER que ficou na entrada na instrução anterior

            if (opcao == 1) {
                // Se não tem mais espaço no vetor, caio fora
                if (qtdCadastrados == MAX_ELEMENTOS) {
                    System.out.println("\nNão há espaço para cadastrar novos pilotos.");
                    voltarMenu(in);
                    continue;
                }

                //Cadastre seu piloto aqui

                System.out.println("\nPiloto cadastrado com sucesso.");
                voltarMenu(in);
            } else if (opcao == 2) {
                // Se não tem ninguém cadastrado no vetor, caio fora
                if (qtdCadastrados == 0) {
                    System.out.println("\nNão há motoristas cadastrados para exibir.");
                    voltarMenu(in);
                    continue;
                }

                // Exiba os pilotos aqui

                voltarMenu(in);
            
            } else if (opcao == 3) {

                System.out.println(x: "Digite o CPF desejado:");
                String cpf2 = in.nextLine();
                 for (int i = 0; i <qtdCadastrados; i++){


                if (pilotos[i].getCpf().equals(cpf2));
                System.out.println(x: "A pessoa procurada é:")    
                System.out.println(pilotos[i])

                if (!pilotos[i]getCpf().equals(nomepilotos) && i == qtdCadastrados -1) {
                     System.out.println(x: "Piloto nao encontrado!");
                 
                }   
                 voltarMenu(in);
                 
                 }
            
            } else if (opcao == 4) {
                
                System.out.println(x: "Digite a quantidade de armazenamento desejada:"); 
                novoElemento = in.nextInt();

                for (int i = 0; ) i < maximoElemento; i++) {
                     novoArmazenamento[i] = pilotos[i]; 

                }
                     maximoElemento = novoElemento;
                     pilotos = novoArmazenamento;
                     voltarMenu(in);
            }

            else if (opcao != 0) {
                System.out.println("\nOpção inválida!");
            }
        } while (opcao != 0);

        System.out.println("Fim do programa!");

        in.close();
    }

    private static void voltarMenu(Scanner in) throws InterruptedException, IOException {
        System.out.println("\nPressione ENTER para voltar ao menu.");
        in.nextLine();

        // Limpa toda a tela, deixando novamente apenas o menu
        if (System.getProperty("os.name").contains("Windows"))
            new ProcessBuilder("cmd", "/c", "cls").inheritIO().start().waitFor();
        else
            System.out.print("\033[H\033[2J");
        
        System.out.flush();
    }
}
