package ejercicioevento;

import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

public class EjercicioEvento extends JFrame {

    double nota1, nota2, nota3, promedio;
    JLabel p1, p2, p3, p4, resultado;
    JTextField v1, v2, v3;
    JButton boton;

    public EjercicioEvento() {

        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        Color colorNew = new Color(6, 14, 118);
        Color resultcolor = new Color(254, 254, 254);
        p1 = new JLabel("Ingrese la primera nota");
        p1.setBounds(50, 25, 210, 70);
        p1.setForeground(Color.WHITE);

        v1 = new JTextField(10);
        v1.setBounds(220, 45, 80, 25);

        p2 = new JLabel("Ingrese la segunda nota");
        p2.setBounds(50, 65, 210, 70);
        p2.setForeground(Color.WHITE);

        v2 = new JTextField(10);
        v2.setBounds(220, 85, 80, 25);

        p3 = new JLabel("Ingrese la tercera nota");
        p3.setBounds(50, 105, 210, 70);
        p3.setForeground(Color.WHITE);

        v3 = new JTextField(10);
        v3.setBounds(220, 125, 80, 25);

        boton = new JButton("Promediar");
        boton.setBounds(150, 200, 110, 30);

        p4 = new JLabel("Su promedio es: ");
        p4.setBounds(130, 220, 200, 100);
        p4.setFont(new Font("Arial", Font.ITALIC, 16));
        p4.setForeground(Color.WHITE);

        resultado = new JLabel();
        resultado.setBounds(100, 300, 200, 30);
        resultado.setFont(new Font("Arial", Font.ITALIC, 18));
        resultado.setForeground(resultcolor);

        Container panel = getContentPane();
        panel.setLayout(null);
        panel.add(p1);
        panel.add(p2);
        panel.add(p3);
        panel.add(p4);
        panel.add(v1);
        panel.add(v2);
        panel.add(v3);
        panel.add(boton);
        panel.add(resultado);
        panel.setBackground(colorNew);

        boton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                nota1 = Double.parseDouble(v1.getText());
                nota2 = Double.parseDouble(v2.getText());
                nota3 = Double.parseDouble(v3.getText());
                promedio = (nota1 + nota2 + nota3) / 3;
                if (promedio >= 4.5) {
                    resultado.setText(String.format("%.1f", promedio) + " EXECELENTE!");
                } else if (promedio > 3.5 && promedio < 4.5) {
                    resultado.setText(String.format("%.1f", promedio) + " APROBADO!");
                } else {
                    resultado.setText(String.format("%.1f", promedio) + " REPROBO!");
                }
            }
        });

    }

    public static void main(String[] args) {

        EjercicioEvento apro = new EjercicioEvento();
        apro.setTitle("Promedio de Notas");
        apro.setVisible(true);
        apro.setSize(450, 450);
        apro.setLocation(250, 100);

    }

}
