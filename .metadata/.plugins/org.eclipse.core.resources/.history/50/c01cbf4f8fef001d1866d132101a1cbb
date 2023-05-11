package estudiantes;

import javax.swing.JOptionPane;

public class Procesos {
	
	String nombres[];
	int edad[];
	int n;
	int sumatoria = 0;	

	public void iniciar() {
		String menu="MENU ESTUDIANTES\n";
		menu+="1. Registrar\n";
		menu+="2. Imprimir\n";
		menu+="3. promedio edades\n";
		menu+="4. estudiantes mayores de edad\n";
		menu+="5. estudiantes menores de edad\n";
		menu+="6. cantidad mayores de edad\n";
		menu+="7. Busqueda por nombre\n";
		menu+="8. Busqueda por edad\n";
		menu+="9 salir\n\n";
		menu+="Ingrese una opción:";
		
		int opc=0;
		do {
			opc=Integer.parseInt(JOptionPane.showInputDialog(menu));
			validarOpcion(opc);
		} while (opc!=9);
	}
	
	private void validarOpcion(int opc) {
			switch (opc) {
			case 1: 
				registrarEstudiantes();
				break;
				
			case 2: validarRegistro(opc);
					/*if (nombres!=null || edad !=null) {
						imprimirEstudiantes();
					}else {
						JOptionPane.showMessageDialog(null, "No hay datos, registrese primero");
					}*/

				break; 
				
			case 3: validarRegistro(opc);

				break;
				
			case 4: validarRegistro(opc);
				break;
				
			case 5: validarRegistro(opc);
				break;
				
			case 6: validarRegistro(opc);
				break;
				
			case 7: validarRegistro(opc);
				break;
				
			case 8: validarRegistro(opc);
				break;
				
			case 9: JOptionPane.showMessageDialog(null, "Gracias por usar el programa!");
				break;
				
			default: JOptionPane.showMessageDialog(null, "No existe el código!");
				break;
			}
	}
	
	public void validarRegistro(int opc) {
		if (nombres!=null || edad !=null) {
			
			switch (opc) {
			case 2: imprimirEstudiantes();
				break;
			case 3: promedioEdades();
				break;
			case 4: estMayoresEdad();
				break;
			case 5: estMenoresEdad();
				break;
			case 6: cantMayoresEdad();
				break;
			case 7: buscarEstudiantePorNombre();
				break;
			case 8: busquedaPorEdad();
			}

		}else {
			JOptionPane.showMessageDialog(null, "No hay datos, registrese primero");
		}
	}
	
	
	private void registrarEstudiantes() {
		n=Integer.parseInt(JOptionPane.showInputDialog("Ingrese la cantidad de estudiantes"));
		nombres= new String[n];
		edad = new int[n];

		for (int i = 0; i < n; i++) {
			nombres[i]=JOptionPane.showInputDialog("Ingrese el nombre # " + (i+1));
			do {
				edad[i] = Integer.parseInt(JOptionPane.showInputDialog("Ingrese la edad de " + nombres[i]));
				
				if(edad[i] < 0 || edad[i] > 100) {
					JOptionPane.showMessageDialog(null, "la edad no debe ser menor a 0 ni mayor a 100, ingresela nuevamnete");
				}
			}while(edad[i] < 0 || edad[i] > 100);
			
			sumatoria += edad[i];
		}
		//System.out.println("sumatoria "+ sumatoria);
	}
	
	
	private void estMayoresEdad() {
		String nombresM = "";
		boolean estado= false;
		
		for (int i = 0; i < n; i++) {
			if(edad[i] >= 18) {
				nombresM += nombres[i] + " con una edad de : " +edad[i] +" años\n";
				estado = true;
			}
		}
		if (estado) {
			JOptionPane.showMessageDialog(null, "listado estudiantes mayores de edad:\n" + nombresM );
		} else {
			JOptionPane.showMessageDialog(null, "listado estudiantes mayores de edad:\n" + "Nadie es mayor de edad");
		}
	}

	
	public void estMenoresEdad() {
		String nombresM = "";
		boolean estado= false;
		
		for (int i = 0; i < n; i++) {
			if(edad[i] < 18) {
				nombresM += nombres[i] + " con una edad de " +edad[i] +" años\n";
				estado = true;
			}
		}
		if (estado) {
			JOptionPane.showMessageDialog(null, "listado estudiantes menores de edad:\n" + nombresM );
		} else {
			JOptionPane.showMessageDialog(null, "listado estudiantes menores de edad:\n" + "Nadie es menor de edad");
		}
	}

	
	public void promedioEdades() {
		double promEdad;
		
		promEdad = sumatoria / n;
		JOptionPane.showMessageDialog(null, "promedio edades: " +promEdad);
		
	}
	
	
	public void cantMayoresEdad() {
		int contador = 0;
		
		for (int i = 0; i < n; i++) {
			if(edad[i] >= 18) {
				contador++;
			}
		}
		JOptionPane.showMessageDialog(null, "cantidad estudiantes mayores de edad : " + contador);
	}
	
	
	public void imprimirEstudiantes() {
		String impresion = "";
		
		for (int i = 0; i < n; i++) {
			impresion += "nombre: "+ nombres[i] +", edad: "+ edad[i] +" años\n";
		}
		JOptionPane.showMessageDialog(null, impresion);
	}
	
	
	public void buscarEstudiantePorNombre() {
		
		String impresion = "";
		int cont=0;
		String nombreBuscar=JOptionPane.showInputDialog("Ingrese el nombre a buscar");
		
		for (int i = 0; i < nombres.length; i++) {

			if (nombres[i].equalsIgnoreCase((nombreBuscar))) {
				impresion += "se encontró en la pos: "+i+ ", tiene " +edad[i] +" años \n";
				cont++;
			}
		}
		
		if (cont>0) {
			JOptionPane.showMessageDialog(null, nombreBuscar + " se encontró "+cont+" veces \n" +impresion);
		}else {
			JOptionPane.showMessageDialog(null, "No se encontró el nombre "+nombreBuscar);
		}
		
	}
	
	
	public void busquedaPorEdad() {
		String nombre = "";
		boolean estado = false;
		int buscarEdad= Integer.parseInt(JOptionPane.showInputDialog("Ingrese la edad a consultar"));
		
		for(int i = 0; i < edad.length; i++) {
			if(edad[i] == buscarEdad) {
				nombre += nombres[i] + "\n";
				estado = true;
			}			
		}
		
		if (estado) {
			JOptionPane.showMessageDialog(null, "estudiantes que tienen la edad de " +buscarEdad+ " años:\n" +nombre);
		} else {
			JOptionPane.showMessageDialog(null, "No se encontró ningun estudiante con la edad de " +buscarEdad + " años"); 
		}
	}
	

	
	/*public void validacion(Object objeto) {
	if (nombres!=null || edad !=null) {
		objeto;
	}else {
		JOptionPane.showMessageDialog(null, "No hay datos, registrese primero");
	}
}*/
}
