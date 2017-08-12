# Note_Android_Property

~~~Java
String androidId = Secure.getString(context.getContentResolver(), "android_id");
Build.BRAND
Build.DEVICE
Build.PRODUCT
MonitorMessages.SDK_VERSION
VERSION.SDK_INT
Build.MODEL
Build.TYPE
params.put("lang", Locale.getDefault().getDisplayLanguage());
params.put("lang_code", Locale.getDefault().getLanguage());
params.put("country", Locale.getDefault().getCountry());
TelephonyManager manager = (TelephonyManager) context.getSystemService("phone");
                params.put("operator", manager.getSimOperatorName());
                params.put("carrier", manager.getNetworkOperatorName());
~~~


~~~C#
 private void button1_Click(object sender, EventArgs e)
        {
            String path = @"C:\Users\Admin\Desktop\SockNguyenNghia.ppx";
            XmlDocument doc = new XmlDocument();
            doc.Load(path);

            // get a list of nodes - in this case, I'm selecting all <AID> nodes under
            // the <GroupAIDs> node - change to suit your needs
            XmlNode proxyNode = doc.SelectNodes("//ProxyList")[0];

            var addressNode = proxyNode.SelectSingleNode("./Proxy/Address");
            var portNode = proxyNode.SelectSingleNode("./Proxy/Port");

            addressNode.InnerText = "127.5.0.1";
            portNode.InnerText = "80";
            // save the XmlDocument back to disk
            doc.Save(path);


            LoadProxiferProfile(@"C:\Program Files (x86)\Proxifier\Proxifier.exe", path);
        }

        private void LoadProxiferProfile(String proxiferPath, String profilePath)
        {
            Process cmd = new Process();
            cmd.StartInfo.FileName = proxiferPath;
            cmd.StartInfo.RedirectStandardInput = true;
            cmd.StartInfo.RedirectStandardOutput = true;
            cmd.StartInfo.CreateNoWindow = true;
            cmd.StartInfo.UseShellExecute = false;
            cmd.StartInfo.Arguments = profilePath + " silent-load";
            cmd.Start();

           
            cmd.WaitForExit();
            
        }
~~~
