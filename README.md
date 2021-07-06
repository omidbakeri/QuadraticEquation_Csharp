<!-- # QuadraticEquation_Csharp
a Quadratic equation System find the roots . -->

/*
 * Created by SharpDevelop.
 * User: LaptopYar
 * Date: 14/04/1400
 * Time: 23:34
 * 
 * To change this template use Tools | Options | Coding | Edit Standard Headers.
 */
using System;
using System.Drawing;
using System.Windows.Forms;

namespace Quadratic_Equation_System
{
	/// <summary>
	/// Description of Form1.
	/// </summary>
	public partial class Form1 : Form
	{
		public Form1()
		{
			//
			// The InitializeComponent() call is required for Windows Forms designer support.
			//
			InitializeComponent();
			
			//
			// TODO: Add constructor code after the InitializeComponent() call.
			//
		}
		
		
		
		void BackPush_Click(object sender, EventArgs e)
		{
			this.Close();
			new MainForm().Show();
		}
		
		void ConfirmationPush_Click(object sender, EventArgs e)
		{
			bool aflag =true;
			bool bflag =true;
			bool cflag =true;
			
			if(txt_a.Text=="")
			{
				aflag=false;
				MessageBox.Show("لطفا ضریب اول را وارد نمایید" , "خطا" , MessageBoxButtons.OK , MessageBoxIcon.Error);	
			}
			if(txt_a.Text!="")
			{
				aflag=true;
			}
			
			double txtNum;
			txtNum = double.Parse(txt_a.Text);
			
			if(txtNum==0)
			{
				aflag = false;
				MessageBox.Show("معادله شما درجه دوم نیست" , "خطا" , MessageBoxButtons.OK , MessageBoxIcon.Warning);	
			}
			
			
			
			if(txt_b.Text=="")
			{
				bflag=false;
				MessageBox.Show("لطفا ضریب دوم را وارد نمایید" , "خطا" , MessageBoxButtons.OK , MessageBoxIcon.Error);	
			}
			if(txt_b.Text!="")
			{
				bflag=true;
			}
			
			
			
			if(txt_c.Text=="")
			{
				cflag=false;
				MessageBox.Show("لطفا ضریب سوم را وارد نمایید" , "خطا" , MessageBoxButtons.OK , MessageBoxIcon.Error);	
			}
			if(txt_c.Text!="")
			{
				cflag=true;
			}
			
			
			double txtNum_a;
			double txtNum_b;
			double txtNum_c;
			
			if(aflag==true  &&  bflag==true  &&  cflag==true)
			{
				txtNum_a = double.Parse(txt_a.Text);
				txtNum_b = double.Parse(txt_b.Text);
				txtNum_c = double.Parse(txt_c.Text);
				
				double delta;
				delta = ((txtNum_b*txtNum_b) - (4 * txtNum_a * txtNum_c));
				
				if(delta<0)
				{
					resEquation.BackColor = Color.Red;
					resEquation.ForeColor = Color.White;
					resEquation.Text= "معادله درجه دوم شما ریشه حقیقی ندارد";
				}
				
				if(delta==0)
				{
					resEquation.BackColor = Color.Orange;
					resEquation.ForeColor = Color.White;
					
					double x1;
					double x2;
					
					x1 = -(txtNum_b)/(2 * txtNum_a);
					x2 = -(txtNum_b)/(2 * txtNum_a);
					
					resEquation.Text = "ریشه های مضاعف معادله شما برابر است با :" + x1.ToString() + " , " +  x2.ToString();
				}
				
				
				if(delta>0)
				{
					
					
					double txnum1;
					double txnum2;
					double txnum3;
					
				    double sqrTrableDoubleChange;
				    
				    txnum1 = double.Parse(txt_a.Text);
				    txnum2 = double.Parse(txt_b.Text);
				    txnum3 = double.Parse(txt_c.Text);
				    
				    sqrTrableDoubleChange = Math.Sqrt(delta);
				    
				    double x_1;
				    double x_2;
				    
				    x_1 = (-(txnum2) + sqrTrableDoubleChange)/(2 * txnum1);
				    x_2 = (-(txnum2) - sqrTrableDoubleChange)/(2 * txnum1);
				    
				    
				    resEquation.BackColor = Color.Green;
				    resEquation.ForeColor = Color.White;
				    resEquation.Text = "معادله مشخصه شما دو ریشه حقیقی غیر برابر " + x_1.ToString() + ", "  + x_2.ToString() + "دارد"; 
				    
				}
				
				
			}
			
			
			
			
			
		}
		
		void ResEquation_Click(object sender, EventArgs e)
		{
			// TODO: Implement ResEquation_Click
		}
	}
}
