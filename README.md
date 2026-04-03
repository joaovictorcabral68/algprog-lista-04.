# Lista 4 

>Foi passado os seguintes exercícios:

1. Um programa que peça uma nota entre 0 e 10, se o número digitado for ínvalido tem que pedir o número novamente.
2. Um programa que peça o número de usúario e a senha, caso a senha for igual ao nome de usúario, aparece uma mensagem de erro e repete o programa.
3. Um programa que leia e valide as seguintes informações:
Nome: maior que 3 caracteres;
Idade: entre 0 e 150;
Salário: maior que zero;
Sexo: 'f' ou 'm';
Estado Civil: 's', 'c', 'v', 'd';
4. Um programa que leia a população de dois países e informe quantas pessoas faltam para a população igualar.
5. Um programa que altere o anterior e permita o usúario populações e as taxas de crescimento.
6. Um programa que imprima os números de 1 à 20 um à baixo do outro e depois imprima um ao lado do outro
7. Um programa que leia 5 números e informe o maior número.
8. Um programa que leia 5 números e informe a soma e a média dos números.
9. Um programa que imprima na tela apenas os números ímpares entre 1 e 50.
10. Um programa que receba dois números inteiros e gere os números inteiros que estão no intervalo compreendido por eles.

## Desenvolvimento

>Para realização desses exercícios eu usei o Visual code com a linguagem `Java` e usei as estruturas: `if/else`, `While`, `for`, 

### 1.

```Java

import java.util.Scanner;

public class Entre{
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        System.out.println("Escreva um número entre 0 e 10");
        int num = sc.nextInt();
        while (num <0 || num>10) {
            System.out.println("Escreva um número entre 0 e 10");
         num = sc.nextInt();
        
    }
          if (num>0 || num < 10) {
            System.out.println("Correto!\nO número digitado foi:" + num);
         System.exit(0);
        
    }
}
}

```

---

### 2.

```Java

import java.util.Scanner;

public class Usuario{
    public static void main(String[] args) {
        Scanner sc= new Scanner(System.in);
        System.out.println("Digite o nome de usuario:");
        String usuario=sc.nextLine();
        System.out.println("Digite sua senha:");
        String senha=sc.nextLine();
        while (usuario.equals(senha)) {
            System.out.println("A senha nao pode ser igual ao nome de usuario, repita novamente:");
            System.out.println("Digite o nome de usuario:");
         usuario=sc.nextLine();
        System.out.println("Digite sua senha:");
         senha=sc.nextLine();
        }
        System.out.println("Correto!\n Seu usuario é:" + usuario +"\nSua senha é:" + senha);

    }
}

```

---

### 3.

```Java

import java.util.Scanner;

public class Validacao{
    public static void main(String[] args) {
        Scanner sc=new Scanner(System.in);
        System.out.println("Escreva seu nome:");
        String nome=sc.nextLine();
        int total=nome.length();
        while (total<3) {
             System.out.println(total);
            System.out.println("O nome tem que ter no mìnimo 3 caracteres.\nRepita por favor:");
             System.out.println("Escreva seu nome:");
          nome=sc.nextLine();
         total=nome.length();
        }
    System.out.println("Correto!\nO nome informado é:" +nome);
    System.out.println("Escreva sua idade:");
    int idade=sc.nextInt();
    while (idade <0 || idade>150) {
        System.out.println("A idade tem que ser entre: 0 à 150 anos\n Repita por favor!:");
        System.out.println("Escreva sua idade:");
        idade=sc.nextInt();
        
    }
    System.out.println("\nCorreto! A sua idade é:" + idade + " anos");
    System.out.println("Qual seu sálario?:");
    int salario=sc.nextInt();
    while (salario==0) {
         System.out.println("Qual seu sálario?:");
    salario=sc.nextInt();
    }
    System.out.println("Correto, seu sálario é de:" + salario+"$");
    System.out.println("Qual seu sexo?:\nF.feminino M.Masculino");
    char sexo=sc.next().charAt(0);
    while(sexo!='f' && sexo!='m'){
    System.out.println("Você só tem a opção de F ou M\nRepita por favor:");
    System.out.println("Qual seu sexo?:\nF.feminino M.Masculino");
     sexo=sc.next().charAt(0);
    }
    System.out.println("Correto! seu sexo é:" +sexo);
    System.out.println("Qual seu estado civil?:\ns\nc\nv\nd");
    char civil=sc.next().charAt(0);
    while (civil!='s' && civil!='c' && civil!='v' && civil!='d') {
        System.out.println("Qual seu estado civil?:\ns\nc\nv\nd");
    civil=sc.next().charAt(0);
    }
    System.out.println("Correto!, seu estado civil é:" + civil);
    System.out.println("Dados salvo com sucesso:\nUsuario:"+ nome + "\nIdade:" + idade +"\nSalario:"+salario+"\nSexo:"+sexo+"\nEstado civil:"+civil);

    }
}

```

---

### 4.

```Java

public class Populacao {
    public static void main(String[] args) {

        double pop1 = 80000;
        double pop2 = 200000;

        int anos = 0;

        while (pop1 < pop2) {
            pop1 = pop2 + (pop1 * 0.03);   
            pop1 = pop2 + (pop2 * 0.015);  
            anos++;
        }

        System.out.println("Anos necessários: " + anos);
        System.out.println("População A: " + (int)pop1);
        System.out.println("População B: " + (int)pop2);
    }
}

```

---

### 5.

```Java

import java.util.Scanner;

public class Populacao {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        char repetir;

        do {
            double popA, popB, taxaA, taxaB;

            
            do {
                System.out.print("Digite a população de A: ");
                popA = sc.nextDouble();
                if (popA <= 0) {
                    System.out.println("Valor inválido!");
                }
            } while (popA <= 0);

            
            do {
                System.out.print("Digite a população de B: ");
                popB = sc.nextDouble();
                if (popB <= 0) {
                    System.out.println("Valor inválido!");
                }
            } while (popB <= 0);

        
            do {
                System.out.print("Digite a taxa de crescimento de A (%): ");
                taxaA = sc.nextDouble();
                if (taxaA <= 0) {
                    System.out.println("Valor inválido!");
                }
            } while (taxaA <= 0);

         
            do {
                System.out.print("Digite a taxa de crescimento de B (%): ");
                taxaB = sc.nextDouble();
                if (taxaB <= 0) {
                    System.out.println("Valor inválido!");
                }
            } while (taxaB <= 0);

            int anos = 0;

          
            while (popA < popB) {
                popA += popA * (taxaA / 100);
                popB += popB * (taxaB / 100);
                anos++;
            }

            System.out.println("Anos necessários: " + anos);

            
            System.out.print("Deseja repetir? (s/n): ");
            repetir = sc.next().charAt(0);

        } while (repetir == 's' || repetir == 'S');

        sc.close();
    }
}

```

---

### 6.

```Java

public class Numeros {
    public static void main(String[] args) {

        // Um abaixo do outro
        System.out.println("Números um abaixo do outro:");
        for (int i = 1; i <= 20; i++) {
            System.out.println(i);
        }

        System.out.println("\nNúmeros lado a lado:");

      
        for (int i = 1; i <= 20; i++) {
            System.out.print(i + " ");
        }
    }
}

```

---

### 7.

```Java

import java.util.Scanner;

public class MaiorNumero {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int num, maior;

        System.out.print("Digite o 1º número: ");
        maior = sc.nextInt();

        for (int i = 2; i <= 5; i++) {
            System.out.print("Digite o " + i + "º número: ");
            num = sc.nextInt();

            if (num > maior) {
                maior = num;
            }
        }

        System.out.println("O maior número é: " + maior);

        sc.close();
    }
}

```

---

### 8.

```Java

import java.util.Scanner;

public class SomaMedia {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int num;
        int soma = 0;

       
        for (int i = 1; i <= 5; i++) {
            System.out.print("Digite o " + i + "º número: ");
            num = sc.nextInt();
            soma += num;
        }

        double media = soma / 5.0;

        System.out.println("Soma: " + soma);
        System.out.println("Média: " + media);

        sc.close();
    }
}

```

---

### 9.

```Java

public class Impares {
    public static void main(String[] args) {

        for (int i = 1; i <= 50; i++) {
            if (i % 2 != 0) {
                System.out.println(i);
            }
        }

    }
}

```

---

### 10.

```Java

import java.util.Scanner;

public class Intervalo {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Digite o primeiro número: ");
        int n1 = sc.nextInt();

        System.out.print("Digite o segundo número: ");
        int n2 = sc.nextInt();

        int menor = Math.min(n1, n2);
        int maior = Math.max(n1, n2);

        System.out.println("Números no intervalo:");

        for (int i = menor + 1; i < maior; i++) {
            System.out.println(i);
        }

        sc.close();
    }
}

```

---


