# Spout 2.006
http://spout.zeal.co/

MODE:GPU(NVIDIA GL/DX interop extension) CPU Memory

SpoutSender:发送器

  SpoutSender.CreateSender:创建一个发送器
    
    SpoutSDK.CreateSender

      SpoutSDK.OpenSpout()
        
        //检测是否支持扩展
        SpoutGLDXinterop.LoadGLextensions:加载NVIDIA的GL/DX扩展：加载FBO的扩展、加载FBO BLIT的扩展、加载交换链的扩展、加载PBO的扩展、找出编译和运行时是否支持bgra的扩展（未测试完）、加载wgl interop的扩展（不需要用来内存共享）
        
        SpoutGLDXinterop.getMemory : 0 GPU, 1 CPU, 2 Memory
        
        //如果不是内存共享 则初始化DX和准备interop
        
      SpoutSDK.CleanSenders();//清除 sender名字存在但共享内存信息不存在的sender
      
      SpoutSDK.InitSender()
        
        if//如果不是memory share，才初始化gl/dx interop和创建一个新的纹理
        SpoutGLDXinterop.CreateInterop //判断dx 9 11格式 设置接收器可以接受dx9的格式
          glGenFramebuffersEXT(1, &m_fbo); //创建出来一个fbo用来复制纹理
          glGenTextures(1, &m_glTexture);//创建出来一个本地的纹理用来连接dx的共享纹理
          SpoutGLDXinterop.CreateDX11interop//创建dx11的 interop
            SpoutDirect.CreateSharedDX11Texture//Usage:default
            //如果是CPU的模式 则创建出一个stage的纹理
            SpoutGLDXinterop.LinkGLDXtextures 将dx纹理链接到gl的纹理上
        else//否则的话  如果这里是一个gl的上下文，加载扩展以便fbo的工作
        //从2.005开始，gl也被用来内存分享，如果扩展加载失败的话，退出

SpoutReceiver:接收器
