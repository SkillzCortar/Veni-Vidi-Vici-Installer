# Veni-Vidi-Vici-Installer
GTA V Online 1.51 PC Mod Menu Installer

private void FuckRockstar()
    {
      if (this.IsProcessOpen("GTA5"))
        this.Killprocess("GTA5");
      if (this.IsProcessOpen("LauncherPatcher"))
        this.Killprocess("LauncherPatcher");
      if (this.IsProcessOpen("Launcher"))
        this.Killprocess("Launcher");
      if (this.IsProcessOpen("RockstarService"))
        this.Killprocess("RockstarService");
      if (!this.IsProcessOpen("SocialClubHelper"))
        return;
      this.Killprocess("SocialClubHelper");
    }

    private void Whitenigger()
    {
      if (this.IsProcessOpen("GTA5") && this.alreadysawmsg == 0)
      {
        int num = (int) MessageBox.Show("[WARNING] GTAV is Open ! Please Close it and press OK", "Veni Vidi Vici Installer");
        this.LogWarning("GTAV is Open ! Please Close it");
        ++this.alreadysawmsg;
      }
      if (this.IsProcessOpen("Launcher"))
      {
        int num = (int) MessageBox.Show("[WARNING] The Rockstargames Launcher is Open ! Please Close it and press OK", "Veni Vidi Vici Installer");
        this.LogWarning("The Rockstargames Launcher is Open ! Please Close it");
      }
      if (this.IsProcessOpen("LauncherPatcher"))
      {
        int num = (int) MessageBox.Show("[WARNING] The Rockstargames LauncherPatcher is Open Close it and press ok!", "Veni Vidi Vici Installer");
        this.LogWarning("The Rockstargames LauncherPatcher is Open Close it and press ok!");
        ++this.alreadysawmsg;
      }
      if (this.IsProcessOpen("RockstarService") && this.alreadysawmsg == 0)
      {
        int num = (int) MessageBox.Show("[WARNING] The RockstarService is Open Close it and press ok!", "Veni Vidi Vici Installer");
        this.LogWarning("The RockstarService is Open Close it and press ok!");
        ++this.alreadysawmsg;
      }
      if (!this.IsProcessOpen("SocialClubHelper") || this.alreadysawmsg != 0)
        return;
      int num1 = (int) MessageBox.Show("[WARNING] The SocialClubHelper is Open Close it and press ok!", "Veni Vidi Vici Installer");
      this.LogWarning("The SocialClubHelper is Open Close it and press ok!");
      ++this.alreadysawmsg;
    }

    private void Form1_Load(object sender, EventArgs e)
    {
      Process.GetCurrentProcess();
      this.Ping_Forum();
      this.Ping_SkillzCortar();
      this.Ping_Server();
      this.Installer_Versionchecker();
      this.Menuversioncheckload();
      this.label3.Text = "Installer V" + this.Currentversion;
      this.label2.Text = this.menustring + this.menuvers;
      this.Whitenigger();
      if (!Directory.Exists(this.Appdata + "/Veni Vidi Vici"))
        Directory.CreateDirectory(this.Appdata + "/Veni Vidi Vici");
      if (!this.Betaversion)
        return;
      this.timer1.Start();
      this.Currentversion = "1.0 BETA";
    }

    private void LogInfo(string msg)
    {
      this.richTextBox1.Text = this.richTextBox1.Text + "\n [INFO] " + msg;
    }

    private void LogWarning(string msg)
    {
      this.richTextBox1.Text = this.richTextBox1.Text + "\n [WARNING] " + msg;
    }

    private void LogError(string msg)
    {
      this.richTextBox1.Text = this.richTextBox1.Text + "\n [ERROR] " + msg;
    }

    private void Form1_FormClosing(object sender, FormClosingEventArgs e)
    {
    }

    private void Uninstall(string location)
    {
      if (System.IO.File.Exists(this.Appdata + "/Veni Vidi Vici/Version.txt"))
      {
        System.IO.File.Delete(this.Appdata + "/Veni Vidi Vici/Version.txt");
        this.LogInfo("removed old Version file");
      }
      if (System.IO.File.Exists(location + "/Uninstall.exe"))
      {
        System.IO.File.Delete(location + "/Uninstall.exe");
        this.LogInfo("removed Uninstall.exe from gtav path");
      }
      if (System.IO.File.Exists(location + "/dsound.dll"))
      {
        System.IO.File.Delete(location + "/dsound.dll");
        this.LogInfo("removed old dsound.dll");
      }
      if (System.IO.File.Exists(Form1.Documents + "/UpP1YrVpA74DW11Y.menu"))
      {
        System.IO.File.Delete(Form1.Documents + "/UpP1YrVpA74DW11Y.menu");
        this.LogInfo("removed old UpP1YrVpA74DW11Y.menu");
      }
      if (System.IO.File.Exists(location + "/venividivici.nig"))
      {
        System.IO.File.Delete(location + "/venividivici.nig");
        this.LogInfo("removed venividivici.nig");
      }
      if (System.IO.File.Exists(location + "/Veni Vidi ViciTextures.nig"))
      {
        System.IO.File.Delete(location + "/Veni Vidi ViciTextures.nig");
        this.LogInfo("removed Veni Vidi ViciTextures.nig");
      }
      if (Directory.Exists(location + "/mods"))
      {
        DirectoryInfo directoryInfo = new DirectoryInfo(location + "/mods");
        foreach (FileSystemInfo file in directoryInfo.GetFiles())
          file.Delete();
        foreach (DirectoryInfo directory in directoryInfo.GetDirectories())
          directory.Delete(true);
        Directory.Delete(location + "/mods");
        this.LogInfo("removed old mods Folder form the GTAV Directory");
      }
      if (Directory.Exists(location + "/Veni Vidi Vici"))
      {
        DirectoryInfo directoryInfo = new DirectoryInfo(location + "/Veni Vidi Vici");
        foreach (FileInfo file in directoryInfo.GetFiles())
        {
          file.Delete();
          this.LogInfo("removed " + file?.ToString());
        }
        foreach (DirectoryInfo directory in directoryInfo.GetDirectories())
          directory.Delete(true);
        Directory.Delete(location + "/Veni Vidi Vici");
        this.LogInfo("removed old Veni Vidi Vici Folder form the GTAV Directory");
      }
      if (Directory.Exists(location + "/Veni Vidi Vici PC"))
      {
        DirectoryInfo directoryInfo = new DirectoryInfo(location + "/Veni Vidi Vici PC");
        foreach (FileInfo file in directoryInfo.GetFiles())
        {
          file.Delete();
          this.LogInfo("removed " + file?.ToString());
        }
        foreach (DirectoryInfo directory in directoryInfo.GetDirectories())
          directory.Delete(true);
        Directory.Delete(location + "/Veni Vidi Vici PC");
        this.LogInfo("Deleted old Veni Vidi Vici PC Folder (in GTAV) Succsessfully");
      }
      if (System.IO.File.Exists(location + "/Read me.txt"))
      {
        System.IO.File.Delete(location + "/Read me.txt");
        this.LogInfo("removed Read me.txt from gtav path");
      }
      if (!Directory.Exists(Form1.Documents))
        return;
      DirectoryInfo directoryInfo1 = new DirectoryInfo(Form1.Documents);
      foreach (FileInfo file in directoryInfo1.GetFiles())
      {
        file.Delete();
        this.LogInfo("removed " + file?.ToString());
      }
      foreach (DirectoryInfo directory in directoryInfo1.GetDirectories())
        directory.Delete(true);
      Directory.Delete(Form1.Documents);
      this.LogInfo("removed old Veni Vidi Vici Folder form the Documents Directory");
    }

    private void InstallDsound(string location)
    {
      string address = !this.Homeserverstate ? "https://twitter.com/Skillz_Cortar/Downloads/Dsound(Veni Vidi Vici).zip" : "https://twitter.com/Skillz_Cortar/s/JKKW22LYxNgySei/download";
      string str1 = "/Dsound(Veni Vidi Vici).zip";
      string str2 = location + "/Dsound(Veni Vidi Vici).zip";
      using (WebClient webClient = new WebClient())
      {
        try
        {
          webClient.DownloadFile(address, location + str1);
          this.LogInfo("Downloaded Dsound.zip file succsessfully");
        }
        catch
        {
          this.LogError("Cant Download the Dsound.zip");
        }
        try
        {
          ZipFile.ExtractToDirectory(str2, location);
          this.LogInfo("unzipped Dsound.zip file succsessfully");
        }
        catch
        {
          this.LogError("Cant Unzip the Dsound.zip");
        }
        try
        {
          System.IO.File.Delete(str2);
          this.LogInfo("removed Dsound.zip file succsessfully");
        }
        catch
        {
          this.LogError("Cant Delete the Dsound.zip");
        }
        if (System.IO.File.Exists(location + "/dsound.dll"))
        {
          this.LogInfo("Downloaded and Installed the Dsound.dll Successfully");
          this.DsoundSuccsess = true;
        }
        else
        {
          this.LogInfo(location + "/dsound.dll");
          this.LogError("The Fucking Dsound is not in the Gta5 Path!");
          this.DsoundSuccsess = false;
        }
      }
    }
