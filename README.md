# word-counter
import java.awt.Color;
import java.awt.Insets;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

public class wordcounter extends JFrame implements ActionListener{
    JLabel l2,l1;
    JTextArea ta;
    JButton wb,cb;
    JButton pad,reset,text,clean;
    JScrollPane scroll;

    


   wordcounter(){
        super("CHARECTER AND WORD COUNTER");
       
       
       l1=new JLabel("CHARECTER:");
       l1.setBounds(50,50,100, 20);
       
       l2=new JLabel("WORDS:");
       l2.setBounds(50, 80, 100, 20);

       
       
       ta=new JTextArea();
       ta.setBounds(50, 110, 500, 200);
       ta.setLineWrap(true);
       ta.setWrapStyleWord(true);
       ta.setMargin(new Insets(3,3 ,3,2));

       scroll = new JScrollPane(ta); 
       scroll.setBounds(50,110, 500, 200); 
       //scroll.setHorizontalScrollBarPolicy(scroll.HORIZONTAL_SCROLLBAR_ALWAYS);
       //scroll.setVerticalScrollBarPolicy(scroll.VERTICAL_SCROLLBAR_ALWAYS);
       

       cb=new JButton("Charecter Count");
       cb.setBounds(50, 320, 90, 30);
       cb.addActionListener(this);

       wb=new JButton("Word Count");
       wb.setBounds(150, 320, 90, 30);
       wb.addActionListener(this);


       pad=new JButton("Pad Color");
       pad.setBounds(250, 320, 90, 30);
       pad.addActionListener(this);

       reset=new JButton("Clear");
       reset.setBounds(350, 320, 90, 30);
       reset.addActionListener(this);

       text=new JButton("Textcolor");
       text.setBounds(450, 320, 90, 30);
       text.addActionListener(this);


        

       
      
        
        add(l1);
        add(l2);
        add(cb);
        add(wb);
        add(ta);
        add(pad);
        add(reset);
        add(text);
        add(scroll);
  
        
        

        setSize(600,400);
        setLayout(null);
        setVisible(true);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setLocation(420,290);
  



   }



  

                

@Override
public void actionPerformed(ActionEvent e) {
       if(e.getSource()==cb){
        String text=ta.getText();
        l1.setText("CHARECTER:"+ text.length());
       
    }else if(e.getSource()==wb){
        String text=ta.getText();
        String words[]=text.split("\\s");
        l2.setText("WORDS:"+ words.length);
       //}

    }else if(e.getSource()==pad){
    Color  c=JColorChooser.showDialog(this,"choose color",Color.BLACK);
        ta.setBackground(c);

    }else if(e.getSource()==text){
     Color c=JColorChooser.showDialog(this,"choose color",Color.BLACK);
     ta.setForeground(c);
    }else if(e.getSource()==reset){

       ta.setText("");

       String text=ta.getText();
        l1.setText("CHARECTER: ");

        String words[]=text.split("");  
        l2.setText("WORDS: ");
         }
       
     
}
   
       public static void main(String[] args) {
            new wordcounter();
       }
     } 

        

