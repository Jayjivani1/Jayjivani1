-using System;
using System.Windows.Forms;

namespace DiamondAutomation
{
    public partial class MainForm : Form
    {
        public MainForm()
        {
            InitializeComponent();
        }

        private void InitializeComponent()
        {
            this.Text = "Diamond 3D Automation System";
            this.Size = new System.Drawing.Size(1200, 800);

            // Data Grid View
            DataGridView gViewStones = new DataGridView
            {
                Location = new System.Drawing.Point(20, 100),
                Size = new System.Drawing.Size(1150, 500),
                AutoSizeColumnsMode = DataGridViewAutoSizeColumnsMode.Fill
            };

            // Add Columns
            gViewStones.Columns.Add("StoneID", "Stone ID");
            gViewStones.Columns.Add("Complete", "Complete");
            gViewStones.Columns.Add("Package", "Package");
            gViewStones.Columns.Add("RenderProgress", "Render Progress (%)");
            gViewStones.Columns.Add("IsRunning", "Is Running");
            gViewStones.Columns.Add("StonePath", "Stone Path");
            gViewStones.Columns.Add("Delete", "Delete");

            // Folder Selection Button
            Button btnSource = new Button
            {
                Text = "Select Source Folder",
                Location = new System.Drawing.Point(20, 20),
                Size = new System.Drawing.Size(150, 30)
            };
            btnSource.Click += (s, e) => MessageBox.Show("Folder Selection Clicked");

            // Path Label
            Label lblPath = new Label
            {
                Text = "Selected Path: None",
                Location = new System.Drawing.Point(180, 25),
                AutoSize = true
            };

            // Process Control Button
            Button btnStartProcessing = new Button
            {
                Text = "Start Processing",
                Location = new System.Drawing.Point(20, 50),
                Size = new System.Drawing.Size(150, 30)
            };
            btnStartProcessing.Click += (s, e) => MessageBox.Show("Processing Started");

            // Always On Top Toggle
            Button btnAlwaysOnTop = new Button
            {
                Text = "Always On Top",
                Location = new System.Drawing.Point(200, 50),
                Size = new System.Drawing.Size(150, 30)
            };
            btnAlwaysOnTop.Click += (s, e) => this.TopMost = !this.TopMost;

            // Add Controls to Form
            this.Controls.Add(gViewStones);
            this.Controls.Add(btnSource);
            this.Controls.Add(lblPath);
            this.Controls.Add(btnStartProcessing);
            this.Controls.Add(btnAlwaysOnTop);
        }
    }
}


