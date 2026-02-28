import java.util.Scanner;
import java.util.Random;
public class POOEX2{
    public int dadosCraps(){
        Random rand = new Random();
        int dado1 = rand.nextInt(6) + 1; 
        int dado2 = rand.nextInt(6) + 1;
        return dado1 + dado2;
    }
    public static void main(String[] args) {
        POOEX2 jogo = new POOEX2();
        
        int soma = jogo.dadosCraps();
        System.out.println("Primeira Rolagem: " + soma);
        
        if(soma == 7 || soma == 11){
            System.out.println("Voce ganhou!");
        } else if(soma == 2 || soma == 3 || soma == 12){
            System.out.println("A casa vence, voce perdeu.");
        } else {
            int pontuacao = soma;
            System.out.println("Pontuação para igualar: " + pontuacao);
            
            while(true){
                int novaSoma = jogo.dadosCraps();
                System.out.println("Nova Soma: " + novaSoma);
                
                if(novaSoma == pontuacao){
                    System.out.println("Voce ganhou!");
                    break;
                } else if(novaSoma == 7){
                    System.out.println("A casa vence, voce perdeu.");
                    break;
                }            
            }
        }
    }
}

