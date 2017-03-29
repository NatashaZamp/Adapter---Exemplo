# Adapter---Exemplo
Atividade

public class TomadaDeDoisPinos {
	public void ligarNaTomadaDeDoisPinos() {
		System.out.println("Ligado na Tomada de Dois Pinos");
	}
}

public class TomadaDeTresPinos {
	public void ligarNaTomadaDeTresPinos() {
		System.out.println("Ligado na Tomada de Tres Pinos");
	}
}

public class AdapterTomada extends TomadaDeDoisPinos {
	private TomadaDeTresPinos tomadaDeTresPinos;

	public AdapterTomada(TomadaDeTresPinos tomadaDeTresPinos) {
		this.tomadaDeTresPinos = tomadaDeTresPinos;
	}

	public void ligarNaTomadaDeDoisPinos() {
		tomadaDeTresPinos.ligarNaTomadaDeTresPinos();
	}
}

-------------------------------------------------------------------------------------------
public class Teste {

	public static void main(String args[]) {
		TomadaDeTresPinos t3 = new TomadaDeTresPinos();
		
		AdapterTomada a = new AdapterTomada(t3);
		a.ligarNaTomadaDeDoisPinos();
	}

}
