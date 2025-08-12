# PO


# negocio 
estante.java

package negocio;

public class Estante {
	// Propriedades da classe
	private int numero = 0;
	
	// Métodos construtures da classe 
	public Estante() {  // VAZIO 
		
		
	}
	
	public Estante(int numero) {   // CHEIO
		this.numero = numero;
	}
	
	// Métodos de acesso da classe
	
	// NUMERO
	public int getNumero() {
		return numero;
	}
	
	public void setNumero(int numero) {
		this.numero = numero; 
	}

}  // FIM DA PRIMEIRA CLASSE




#PRODUTO.JAVA
package negocio;

public class Produto {
	// Propriedades da classe
	private String nome = "";
	private Estante objEstante = null;
	private int quantidade = 0;

	// Métodos construtores da classe (Usando: Generate Constructor using fields)
	public Produto() {  // VAZIO

	}

	public Produto(String nome, Estante objEstante, int quantidade) {  // CHEIO
		this.nome = nome;
		this.objEstante = objEstante;
		this.quantidade = quantidade;
	}

	// Métodos de acessos da classe (Usando: Generate getters and setters)

	// PARA NOME
	public String getNome() { // CHEIO
		return nome;
	}

	public void setNome(String nome) {
		this.nome = nome;
	}

	
	// PARA ESTANTE
	public Estante getObjEstante() {
		return objEstante;
	}

	public void setObjEstante(Estante objEstante) {
		this.objEstante = objEstante;
	}

	
	// PARA QUANTIDADE
	public int getQuantidade() {
		return quantidade;
	}

	public void setQuantidade(int quantidade) {
		this.quantidade = quantidade;
	}

}

APRESENTAÇÃO

package apresentacao;

import java.io.BufferedReader;
import java.io.InputStreamReader;

import negocio.Estante;
import negocio.Produto;

public class VisaoControleEstoque {
	public static void main(String[]args) {
		//Declaração de variáveis
		BufferedReader leitor = new BufferedReader(
				                new InputStreamReader(System.in));
		Produto objProduto = new Produto();
		
		// Entrada de dados
		try {
			System.out.print("Digite o nome do produto: ");
			objProduto.setNome(leitor.readLine());
		
			System.out.print("Digite o número da estante:" );
				objProduto.setObjEstante(new Estante(
					        Integer.parseInt(leitor.readLine())));
				
			System.out.print("Digite a quantidade: ");
			objProduto.setQuantidade(
								Integer.parseInt(leitor.readLine()));
			
		} catch (Exception erro) {
			System.out.println(erro);
		}
		
		// Saída de dados
		System.out.println("Nome: " + objProduto.getNome());
		System.out.println("Estante: " + 
							objProduto.getObjEstante().getNumero());
		System.out.println("Quantidade: " + 
						   objProduto.getQuantidade());
	}
}
