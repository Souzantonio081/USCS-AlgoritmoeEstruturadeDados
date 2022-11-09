# USCS-AlgoritmoeEstruturadeDados

\\Main.java

class Main{
    public static void main(String []args){
        tadFila f = new tadFila();
        
        f.enfileirar(8);
        f.enfileirar(9);
        f.enfileirar(10);
        f.imprimir();
        if (f.cheia())
        {
            
             System.out.println("Fila Cheia");
        }
        
        
        
        
    }
}

\\TadFila.java

public class tadFila{

    int inicio;
    int fim;
    int capacidade;
    int dados[];
   
    public tadFila(){
        inicio = -1;
        fim = -1;
        capacidade = 3;
        dados = new int[3];
    }
    
    public void enfileirar(int n){
        cheia();
        if(!cheia()){
            fim++;
            dados[fim] = n;
        }
    }
    
    public void imprimir(){
        for (int i = inicio + 1; i <= fim; i++ ){
            System.out.println(dados[i]);
        }
        System.out.println();
    }
    
    public int desenfilerar(){
        inicio++;
        return dados[inicio];
    }
    
    public int conta(){
        return (fim - inicio);
    }
    
    public boolean vazia(){
        return (conta()==0);
    }
    
    public boolean cheia(){
        return (fim == (capacidade - 1));
    }
}

\\Main.java

class Main {
  public static void main(String[] args) {
    TadFilaPessoa f = new TadFilaPessoa();
    Pessoa q = new Pessoa(23, 'M', "Lucas");
    Pessoa p = new Pessoa(20, 'F', "Giulia");
    Pessoa r = new Pessoa(20, 'F', "Giuli");

    f.enfila(q);
    f.enfila(p);
    f.enfila(r);
    
    f.imprime();

    System.out.println(" quantidade " + f.conta());

  }
}

\\Pessoa.java
class Pessoa{
  int idade;
  char sexo;
  String nome;

  public Pessoa(int i, char s, String n){
      idade = i;
      sexo = s;
      nome= n;
    }

  void imprime(){
    System.out.print("Nome: "+nome+", idade: "+idade+", Sexo: "+sexo);
    System.out.print("\n");
  }
}

\\TadFilaPessoa.java

public class TadFilaPessoa{
    
    int fim;
    int inicio;
    int capacidade = 6;
    Pessoa dados[];

    public TadFilaPessoa(){
        this.fim = -1;
        this.inicio = -1;
        this.dados = new Pessoa[capacidade];
    }

	  public boolean enfila (Pessoa p) {
      if(!cheia()){
        fim++;
	      dados[fim] = p;
        return true;
      }
      return false;
	   }

    public Pessoa desenfila (){
      Pessoa p = null;
      if(vazia()){
        inicio++;
        p = dados[inicio];
        }
      return p;
    }

    public void imprime () {
	      for (int i= 0; i<=fim ; i++){
	        dados[i].imprime();
        }
	  }
      
	   public boolean cheia() {
	       return (fim == capacidade);
	   }

     public boolean vazia(){
       return (fim <= inicio);
     }

    public int conta(){
      return (fim - inicio);
    }
	
}

/******************************************************************************

Autor: Antonio
Data: 16/09/2022

Adicionando pessoas em uma fila

*******************************************************************************/
public class Main
{
	public static void main(String[] args) {
		FilaPessoa f = new FilaPessoa(100);
		FilaPessoa nnIdoso = new FilaPessoa(100);
		FilaPessoa idoso = new FilaPessoa(100);
		
		Pessoa p1 = new Pessoa(20, 'M', "Richard");
		Pessoa p2 = new Pessoa(18, 'M', "Andrew");
		Pessoa p3 = new Pessoa(65, 'M', "Rogério");
		
		f.enfileira(p1);
		f.enfileira(p2);
		f.enfileira(p3);
		
		f.desmembra(idoso, nnIdoso);
		
		System.out.println("Quantidade de pessoas: " + nnIdoso.conta());
		nnIdoso.imprime();
		idoso.imprime();
	}
}
class Pessoa
{
    int idade;
    char sexo;
    String nome;
    
    public Pessoa (int i, char s, String n)
    {
        idade = i;
        sexo = s;
        nome = n;
    }
    
    void imprime ()
    {
        System.out.println("Nome: " + nome + ". Idade: " + idade + ". Sexo: " + sexo);
    }
}

class FilaPessoa
{
    Pessoa dados[];
    int inicio, fim, capacidade;
    
    public FilaPessoa (int n)
    {
        capacidade = n;
        inicio = -1;
        fim = -1;
        dados = new Pessoa[capacidade];
    }
    
    public void enfileira (Pessoa p)
    {
        if (!cheia())
        {
            fim++;
            dados[fim] = p;
        }
    }
    
    public Pessoa desenfileira ()
    {
        inicio++;
        return dados[inicio];
    }
    
    public void imprime ()
    {
        for (int i = inicio + 1; i <= fim; i++)
        {
            dados[i].imprime();
        }
    }
    
    public boolean cheia ()
    {
        return (fim == capacidade - 1);
    }
    
    public boolean vazia()
    {
        return (conta() == 0);
    }
    
    public int conta ()
    {
        return fim - inicio;
    }
    
    public void desmembra (FilaPessoa n1, FilaPessoa n2)
    {
        for (int i = inicio + 1; i <= fim; i++)
        {
            if (dados[i].idade >= 60)
            {
                n1.enfileira(dados[i]);
            }
            else
            {
                n2.enfileira(dados[i]);
            }
            desenfileira();
        }
    }
}

public class Main
{
    public static void main(String[] args){
        
        No n1 = new No(1);
        No n2 = new No(2);
        n1.imprimedado();
        n2.imprimedado();
        
    }


}

public class No{
    int dados;
    No proximo;
    
    public No (int d){
        dados = d;
        proximo = null;
    }
    
    void imprimedado(){
        
        System.out.println("Dado = " + dados);
    }
    
}

public class Lista{
    No inicio;
    
    public Lista(){
        inicio = null;
    }
    
    public void insereNoFinal(No aux){
        if (vazia()){
            inicio = aux;
        }
        else{
            No atual;
            atual = inicio;
            while(atual.proximo != null){
                atual.proximo =aux;
            }
            atual.proximo = aux;
        }
    }
    public boolean vazia(){
        return (inicio == null);
        
    }
    public void imprime(){
        
    }
}


