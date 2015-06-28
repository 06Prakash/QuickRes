
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintStream;
import java.util.Calendar;
import java.util.Date;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.Scanner;

import javax.swing.*;


public class QuickResumeUp1 extends JFrame{
/**
	 * 
	 */
	private static final long serialVersionUID = 1L;
JTextField name=new JTextField(30); 		JTextField addr1=new JTextField(100);
JTextField Mob_no=new JTextField(12); 		JTextField addr2=new JTextField(100);
JTextField mailId=new JTextField(30); 		JTextField father=new JTextField(30);
JTextField mail_dom=new JTextField(30); 	JTextField mother=new JTextField(30);
JTextField City=new JTextField(30); 		JTextField Cert1=new JTextField(30);
JTextField State=new JTextField(30); 		JTextField Cert2=new JTextField(30);
JTextField Country=new JTextField(30); 		JTextField Cert3=new JTextField(30);
JTextField Proj1=new JTextField(50); 		JTextField proj2=new JTextField(50);
JTextField proj1_desc=new JTextField(300); 	JTextField proj2_desc=new JTextField(300);
JTextField proj1_tools=new JTextField(100); JTextField proj2_tools=new JTextField(100);
JTextField proj3=new JTextField(50); 		JTextField proj4=new JTextField(50);
JTextField proj3_desc=new JTextField(300);	JTextField proj4_desc=new JTextField(300);
JTextField proj3_tools=new JTextField(100);	JTextField proj4_tools=new JTextField(100);
JTextField edu1_title=new JTextField(30);	JTextField edu2_title=new JTextField(30);
JTextField edu1_inst=new JTextField(30);	JTextField edu2_inst=new JTextField(30);
JTextField edu1_yop=new JTextField(30);		JTextField edu2_yop=new JTextField(30);
JTextField edu1_perc=new JTextField(30);	JTextField edu2_perc=new JTextField(30);
JTextField edu3_title=new JTextField(30);	JTextField edu4_title=new JTextField(30);
JTextField edu3_inst=new JTextField(30);	JTextField edu4_inst=new JTextField(30);
JTextField edu3_yop=new JTextField(30);		JTextField edu4_yop=new JTextField(30);
JTextField edu3_perc=new JTextField(5);		JTextField edu4_perc=new JTextField(5);
JTextField obj=new JTextField(100); 		JTextField Job=new JTextField(30);
JTextField company=new JTextField(30);		JTextField Year=new JTextField(6);

JButton submit=new JButton("Submit");				JButton reset=new JButton("Reset");
JButton cancel=new JButton("Exit");
JPanel p=new JPanel();
JFrame frame = new JFrame("Resume Creator");

PrintStream fileStream =null;
Scanner in =new Scanner(System.in);
Date d=new Date();
int year = Calendar.getInstance().get(Calendar.YEAR);
boolean status=true;
String Name=null;		String mob_no=null;	    String mail_Id=null;
String addrLine2=null;	String proj=null;		String proj_title=null;
String Obj=null;		String education=null; 		
String resume=null;     String Choice;			String tools=null;
String addrLine1=null;	String city=null;		String state=null;
String country=null;	String cert1=null;
String altrMail=null;	String cert2=null;		String proj1=null;		
String proj_title1=null;String tools1=null;		String cert3=null;
String edu1=null; 		double edu1_per=0;   	String edu1_ins=null; 
int edu1_year=0; 		String edu2_ins=null; 	int edu2_year=0;
String edu2=null; 		double edu3_per=0;		String edu3_ins=null;
int edu3_year=0;	 	String edu3=null;   	double edu2_per=0;
String job1=null; 		int job1_tot=0;			String job1_comp=null;

JLabel lname=new JLabel("Name"); 					JLabel laddr1=new JLabel("Address For Communication");
JLabel lmob_no=new JLabel("Mobile No");				JLabel laddr2=new JLabel("Present Address");
JLabel lmailId=new JLabel("EMail ID"); 				JLabel lfather=new JLabel("Father Name");
JLabel lmail_dom=new JLabel("Domain"); 				JLabel lmother=new JLabel("Mother Name");
JLabel lcity=new JLabel("City"); 					JLabel lcert1=new JLabel("Certification 1 Name");
JLabel lstate=new JLabel("State"); 					JLabel lcert2=new JLabel("Certification 2 Name");
JLabel lcountry=new JLabel("Country"); 				JLabel lcert3=new JLabel("Certification 3 Name");
JLabel lproj1=new JLabel("Project Title"); 			JLabel lproj2=new JLabel("Project Title");
JLabel lproj1_desc=new JLabel("Description");		JLabel lproj2_desc=new JLabel("Description");
JLabel lproj1_tools=new JLabel("Tools");			JLabel lproj2_tools=new JLabel("Tools");
JLabel lproj3=new JLabel("Project Title"); 			JLabel lproj4=new JLabel("Project Title");
JLabel lproj3_desc=new JLabel("Description");		JLabel lproj4_desc=new JLabel("Description");
JLabel lproj3_tools=new JLabel("Tools");			JLabel lproj4_tools=new JLabel("Tools");
JLabel ledu1_title=new JLabel("Title");				JLabel ledu2_title=new JLabel("Title");
JLabel ledu1_inst=new JLabel("Institution Name");	JLabel ledu2_inst=new JLabel("Institution Name");
JLabel ledu1_yop=new JLabel("Year Of Passing");		JLabel ledu2_yop=new JLabel("Year Of Passing");
JLabel ledu1_perc=new JLabel("Percentage");			JLabel ledu2_perc=new JLabel("Percentage");
JLabel ledu3_title=new JLabel("Title");				JLabel ledu4_title=new JLabel("Title");
JLabel ledu3_inst=new JLabel("Institution Name");	JLabel ledu4_inst=new JLabel("Institution Name");
JLabel ledu3_yop=new JLabel("Year of Passing");		JLabel ledu4_yop=new JLabel("Year of Passing");
JLabel ledu3_perc=new JLabel("Percentage");			JLabel ledu4_perc=new JLabel("Percentage");
JLabel lobj=new JLabel("Objective"); 				JLabel job=new JLabel("Your Last Job Name/Title");
JLabel lcompany=new JLabel("Your Last Company");	JLabel lyear=new JLabel("Experience (in Months)");

public QuickResumeUp1() {
		// TODO Auto-generated constructor stub
	
	
	setLayout(new GridLayout(50,50));
	add(lname);				add(name);		
	add(lmob_no);			add(Mob_no);
	add(lmailId);			add(mailId);		
	add(lfather);			add(father);
	add(lmother);			add(mother);	
	add(laddr1);			add(addr1);
	add(laddr2);			add(addr2);		
	add(lcity);				add(City);
	add(lstate);			add(State);	
	add(lcountry);			add(Country);
	add(ledu1_title);		add(edu1_title);
	add(ledu1_inst);		add(edu1_inst);
	add(ledu1_yop);			add(edu1_yop);	
	add(ledu1_perc);		add(edu1_perc);
	add(ledu2_title);		add(edu2_title);
	add(ledu2_inst);		add(edu2_inst);
	add(ledu2_yop);			add(edu2_yop);	
	add(ledu2_perc);		add(edu2_perc);
	add(ledu3_title);		add(edu3_title);
	add(ledu3_inst);		add(edu3_inst);
	add(ledu3_yop);			add(edu3_yop); 
	add(ledu3_perc);		add(edu3_perc);
	add(ledu4_title);		add(edu4_title);
	add(ledu4_inst);		add(edu4_inst);
	add(ledu4_yop);		add(edu4_yop);
	add(ledu4_perc);		add(edu4_perc);
	add(lproj1);			add(Proj1);		
	add(lproj1_desc); 	add(proj1_desc);
	add(lproj1_tools);	add(proj1_tools);	
	add(lproj2);			add(proj2);
	add(lproj2_desc); 	add(proj2_desc); 	
	add(lproj2_tools); 	add(proj2_tools);
	add(lproj3);			add(proj3);	
	add(lproj3_desc); 	add(proj3_desc);
	add(lproj3_tools);	add(proj3_tools);
	add(lproj4);			add(proj4);
	add(lproj4_desc); 	add(proj4_desc);	
	add(lproj4_tools);	add(proj4_tools);
	add(lcert1);			add(Cert1);	
	add(lcert2);			add(Cert2);
	add(lcert3);			add(Cert3);	
	add(lobj);			add(obj);
	add(job);				add(Job);
	add(lcompany);		add(company);
	add(lyear);			add(Year);
	add(submit,BorderLayout.SOUTH); 
	add(reset,BorderLayout.SOUTH);
	add(cancel,BorderLayout.SOUTH);
	setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	frame.setSize(1200,1000);
	add(p,BorderLayout.CENTER);
	pack();
	}
public void getDetails() throws IOException
{
	//Scanner in =new Scanner(System.in);
	
		
submit.addActionListener(new ActionListener() {
	
	@Override
	public void actionPerformed(ActionEvent e) {
		// TODO Auto-generated method stub
		
	
		Name=name.getText();

		if(!(Mob_no.getText().length()<10 || Mob_no.getText().length()>10)){
			mob_no=Mob_no.getText();
		}
		
		mail_Id=mailId.getText();
		
		proj_title=Proj1.getText();

		proj=proj1_desc.getText();

		tools=proj1_tools.getText();

		proj_title1=proj2.getText();

		proj1=proj2_desc.getText();

		tools1=proj2_tools.getText();
	
		addrLine1=addr1.getText();

		addrLine2= addr2.getText();
if(addrLine1.equalsIgnoreCase(addrLine2)){
	addrLine2=" ";
}
		city=City.getText();

		state=State.getText();
		
		country=Country.getText();
	
		cert1=Cert1.getText();
	
		cert2=Cert2.getText();
	
		cert3=Cert3.getText();
	
	
		edu1=edu1_title.getText();
	
		edu1_ins=edu1_inst.getText();
	
		edu1_year=Integer.parseInt(edu1_yop.getText());
		
		edu1_per=Double.parseDouble(edu1_perc.getText());
	
		edu2=edu2_title.getText();
	
		edu2_ins=edu2_inst.getText();

		edu2_year=Integer.parseInt(edu2_yop.getText());
		
		edu2_per=Double.parseDouble(edu2_perc.getText());
	
		edu3=edu3_title.getText();
	
		edu3_ins=edu3_inst.getText();
	
		edu3_year=Integer.parseInt(edu3_yop.getText());
		
		edu3_per=Double.parseDouble(edu3_perc.getText());
	if(edu1_year<=year && edu2_year<=year && edu3_year<=year){
			status=false;
		}
		job1=Job.getText();

		job1_comp=company.getText();

		job1_tot=Integer.parseInt(Year.getText());


			Obj=obj.getText();
	

		
String []resume1={Name ," EMAIL ID : "+mail_Id, "ALT.MAILID :"+altrMail,
					"   "+addrLine1,"   "+city,"   "+state,"   "+country,
					"   "+mob_no, "OBJECTIVE:","     	"+Obj,
					"JOB EXPERIENCE",job1+"	"+job1_comp+"	"+job1_tot,
					"EDUCATIONAL QUALIFICATION","Qualification		Institution			Percentage	YOP",
					edu1+"	 "+edu1_ins+" 			"+String.valueOf(edu1_per)+"		"+String.valueOf(edu1_year),
					edu2+"	 "+edu2_ins+"			"+String.valueOf(edu2_per)+"		"+String.valueOf(edu2_year),
					edu3+"	 "+edu3_ins+"			"+String.valueOf(edu3_per)+"		"+String.valueOf(edu3_year),
					" PROJECT DETAILS", "TITLE : "+proj_title,"DESCRIPTION", proj,
					"Tools : "+tools," ","TITLE : "+proj_title1,"DESCRIPTION", proj1,"Tools : "+tools1,
					"CERTIFICATIONS LIST","   	"+cert1,"    	"+cert2,"    	"+cert3};
			
			PrintStream fileStream;
			try {
				fileStream = new PrintStream(new File("E:\\genResume.txt"));
				for (String resume2: resume1) {
					fileStream.println(resume2);
					fileStream.println(" ");
			}} catch (FileNotFoundException e1) {
				// TODO Auto-generated catch block
				e1.printStackTrace();
			}
			
			
	
	}
	});
}
/**
	 * @param args
	 * @throws IOException 
	 */
	public static void main(String[] args) throws IOException {
		// TODO Auto-generated method stub
QuickResumeUp1 qr=new QuickResumeUp1();
qr.setVisible(true);
do{
	qr.getDetails();
}while(qr.status);

	}
}
