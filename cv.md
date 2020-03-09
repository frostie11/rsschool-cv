My name is Alex Morozik.I live in Grodno and studing in Grodno State University.I am 19 years old.Speaking about my personal skills I can tell that I easy to train, communicative, hard working, like develop my skills every day, and it so good, because in our modern word we have high competition and it means that we should work hard, be strong to have good and well payed job.That think inspired me to become a great programmer, because it is very interesting, exciting, and makes analytics and creative mindset, helps you to find something new for you every day, it is like some kind of the culture, because it is great opportunity to create and leave something after yourself in this world. Speaking about my programming skills, i know on the medium level programming languages such as c++,c#,java.Also I studing to work with data bases in Oracle and access. Example of my works. The game XO using System; using System.Collections.Generic; using System.ComponentModel; using System.Data; using System.Drawing; using System.Linq; using System.Text; using System.Threading.Tasks; using System.Windows.Forms;

namespace WindowsFormsApp1 { public partial class Form1 : Form {

private int x = 12, y = 12;
private Button[,] buttons = new Button[3, 3];
private int player;
public Form1()
{
InitializeComponent();
this.Height = 700;
this.Width = 900;
player = 1;
label1.Text = "Текущий ход: Игрок 1";
for (int i = 0; i < buttons.Length / 3; i++)
{
for (int j = 0; j < buttons.Length / 3; j++)
{
buttons[i, j] = new Button();
buttons[i, j].Size = new Size(200, 200);
}
}
setButtons();

}

private void setButtons()
{
for (int i = 0; i < 3; i++)
{
for (int j = 0; j < 3; j++)
{
buttons[i, j].Location = new Point(12 + 206 * j, 12 + 206 * i);
buttons[i, j].Click += button1_Click;
buttons[i, j].Font = new Font(new FontFamily("Microsoft Sans Serif"), 138);
buttons[i, j].Text = "";
buttons[i, j].Enabled = true;
this.Controls.Add(buttons[i, j]);
}
}
}

private void reloadButtons()
{
for (int i = 0; i < 3; i++)
{
for (int j = 0; j < 3; j++)
{
buttons[i, j].Text = "";
buttons[i, j].Enabled = true;
}
}
}
private void button1_Click(object sender, EventArgs e)
{
switch (player)
{
case 1:
sender.GetType().GetProperty("Text").SetValue(sender, "x");
player = 2;
label1.Text = "Текущий ход: Игрок 2";
break;
case 2:
sender.GetType().GetProperty("Text").SetValue(sender, "o");
player = 1;
label1.Text = "Текущий ход: Игрок 1";
break;
}
sender.GetType().GetProperty("Enabled").SetValue(sender, false);
checkWin();
}
private void checkWin()
{

if (buttons[0, 0].Text == buttons[0, 1].Text && buttons[0, 1].Text == buttons[0, 2].Text)
{

if (buttons[0, 0].Text != "")
{
MessageBox.Show("Победил "+Convert.ToString(player-1)+" игрок!");
reloadButtons();
}
}
if (buttons[1, 0].Text == buttons[1, 1].Text && buttons[1, 1].Text == buttons[1, 2].Text)
{
if (buttons[1, 0].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
if (buttons[2, 0].Text == buttons[2, 1].Text && buttons[2, 1].Text == buttons[2, 2].Text)
{
if (buttons[2, 0].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
if (buttons[0, 0].Text == buttons[1, 0].Text && buttons[1, 0].Text == buttons[2, 0].Text)
{
if (buttons[0, 0].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
if (buttons[0, 1].Text == buttons[1, 1].Text && buttons[1, 1].Text == buttons[2, 1].Text)
{
if (buttons[0, 1].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
if (buttons[0, 2].Text == buttons[1, 2].Text && buttons[1, 2].Text == buttons[2, 2].Text)
{
if (buttons[0, 2].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
if (buttons[0, 0].Text == buttons[1,
messagebox.show
MessageBox.Show
1].Text && buttons[1, 1].Text == buttons[2, 2].Text)
{
if (buttons[0, 0].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
if (buttons[2, 0].Text == buttons[1, 1].Text && buttons[1, 1].Text == buttons[0, 2].Text)
{
if (buttons[2, 0].Text != "")
{
MessageBox.Show("Победил " + Convert.ToString(player-1) + " игрок!");
reloadButtons();
}
}
}

private void chekDrow()
{
if ((buttons[0, 0].Enabled == false) && (buttons[0, 1].Enabled == false) && (buttons[0, 2].Enabled == false) && (buttons[1, 0].Enabled == false) && (buttons[1, 1].Enabled == false) && (buttons[1, 2].Enabled == false) && (buttons[2, 0].Enabled == false) && (buttons[2, 1].Enabled == false) && (buttons[2, 2].Enabled == false))
{
setButtons();
MessageBox.Show("Ничья!");
}
else return;
}

private void buttonPlay_Click(object sender, EventArgs e)
{
for (int i = 0; i < 3; i++)
{
for (int j = 0; j < 3; j++)
{
buttons[i, j].Text = "";
buttons[i, j].Enabled = true;
}
}
}
}
}