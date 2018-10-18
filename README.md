# Parcial-
package practica;
 import java.util.Scanner;
 public class contador { 
private int cont; 
public contador() { 
}
 public contador(int cont) {
 if (cont < 0) { 
this.cont = 0; 
} else {
 this.cont = cont; 
}
 }
 public contador(final contador c) { 
cont = c.cont;
 }
 public int GetContador() {
 return cont;
 }
 public void SetContador(int cont) {
 if (cont < 0) {
 this.cont = 0; 
} else {
 this.cont = cont;
 }
 }
 public void incrementar() {
 cont++; 
}
 public void decrementar() { 
cont--;
 if (cont < 0) {
 cont = 0; 
}
 }
 public static void main(String[] args) {
 Scanner sc = new Scanner(System.in);
 contador contador1 = new contador();
 int tcl; 
System.out.println("Dame un valor para iniciar contador: "); 
tcl = sc.nextInt(); 
contador1.SetContador(tcl);
contador1.incrementar();
 System.out.println(contador1.GetContador());
 contador1.incrementar();
 contador1.incrementar(); 
System.out.println(contador1.GetContador());
 contador1.decrementar();
 System.out.println(contador1.GetContador());
 contador contador2 = new contador(10);
 contador2.incrementar();
 System.out.println(contador2.GetContador()); 
contador2.decrementar();
 System.out.println(contador2.GetContador());
 contador contador3 = new contador(contador2); System.out.println(contador3.GetContador());
 }}




#Problema 2
 
public class fecha { 
 
    private int dia; 
    private int mes; 
    private int year; 
 
    public fecha() { 
    } 
 
    public fecha(int dia, int mes, int year) { 
        this.dia = dia; 
        this.mes = mes; 
        this.year = year; 
    } 
 
     
    public void setDia(int d) { 
        dia = d; 
    } 
    public void setMes(int m) { 
        mes = m; 
    } 
    public void setyear(int a) { 
        year = a; 
    } 
    public int getDia() { 
        return dia; 
    } 
    public int getMes() { 
        return mes; 
    } 
    public int getyear() { 
        return year; 
    } 
 
    
    public boolean fechaCorrecta() { 
        boolean diaCorrecto, mesCorrecto, yearCorrecto; 
        yearCorrecto = year > 0; 
        mesCorrecto = mes >= 1 && mes <= 12; 
        switch (mes) { 
            case 2: 
                if (esBisiesto()) { 
                    diaCorrecto = dia >= 1 && dia <= 29; 
                } else { 
                    diaCorrecto = dia >= 1 && dia <= 28; 
                } 
                break; 
            case 4: 
            case 6: 
            case 9: 
            case 11: 
                diaCorrecto = dia >= 1 && dia <= 30; 
                break; 
            default: 
                diaCorrecto = dia >= 1 && dia <= 31; 
        } 
        return diaCorrecto && mesCorrecto && yearCorrecto; 
    } 
 
     
    private boolean esBisiesto() { 
        return (year % 4 == 0 && year % 100 != 0 || year % 400 == 0); 
    } 
 
    
    public void diaSiguiente() { 
        dia++; 
        if (!fechaCorrecta()) { 
            dia = 1; 
            mes++; 
            if (!fechaCorrecta()) { 
                mes = 1; 
                year++; 
            } 
 
        } 
    } 
 
     
    @Override 
    public String toString() { 
        StringBuilder sb = new StringBuilder(); 
        if (dia < 10) { 
            sb.append("0"); 
        } 
        sb.append(dia); 
        sb.append("-"); 
        if (mes < 10) { 
            sb.append("0"); 
        } 
        sb.append(mes); 
        sb.append("-"); 
        sb.append(year); 
        return sb.toString(); 
    } 
}  
 
 
import java.util.Scanner; 
 
public class ProyectoFecha { 
 
    public static void main(String[] args) { 
        Scanner sc = new Scanner(System.in); 
        int d, m, a; 
 
 
        System.out.println("Introduce fecha: "); 
        System.out.print("dia: "); 
        d = sc.nextInt(); 
        System.out.print("mes: "); 
        m = sc.nextInt(); 
        System.out.print("ano: "); 
        a = sc.nextInt(); 
 
       
        fecha fecha = new fecha(d,m,a); 
 
        if (fecha.fechaCorrecta()) {  
            System.out.println("Fecha introducida: " + fecha); 
 
            
            System.out.println("Los 10 dias siguientes son:"); 
            for (int i = 1; i <= 10; i++) { 
                fecha.diaSiguiente(); 
                System.out.println(fecha); 
            } 
 
        } else { 
            System.out.println("Fecha no valida"); 
        } 
    } 
}



#Problema 3

 
 

 

 

 

 

 

 

 

 

 

 

