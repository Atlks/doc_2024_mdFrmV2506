Jquery .net web webBrowser 兼容问题


<meta http-equiv="X-UA-Compatible" content="IE=edge" />

      /*
       * 
       * 
       *  传入 11000 是 IE11, 9000 是 IE9, 只不过当试着传入 6000 时, 理应是 IE6, 
       *  可实际却是 Edge, 这时进一步测试, 当传入除 IE 现有版本以外的一些数值时 WebBrowser 都使用 Edge 内核
       *  */
      /// <summary>
      /// 修改注册表信息使WebBrowser使用指定版本IE内核
      /// </summary>
      public static void SetFeatures(UInt32 ieMode)
      {
          if (LicenseManager.UsageMode != LicenseUsageMode.Runtime)
          {
              throw new ApplicationException();
          }
          //获取程序及名称
          string appName = System.IO.Path.GetFileName(System.Diagnostics.Process.GetCurrentProcess().MainModule.FileName);
          string featureControlRegKey = "HKEY_CURRENT_USER\\Software\\Microsoft\\Internet Explorer\\Main\\FeatureControl\\";
          //设置浏览器对应用程序(appName)以什么模式(ieMode)运行
          Registry.SetValue(featureControlRegKey + "FEATURE_BROWSER_EMULATION", appName, ieMode, RegistryValueKind.DWord);
          //不晓得设置有什么用
        //  Registry.SetValue(featureControlRegKey + "FEATURE_ENABLE_CLIPCHILDREN_OPTIMIZATION", appName, 1, RegistryValueKind.DWord);
      }
