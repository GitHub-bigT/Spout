# Spout 2.006
http://spout.zeal.co/

MODE:GPU(NVIDIA GL/DX interop extension) CPU Memory

SpoutSender:发送器

  SpoutSender.CreateSender:创建一个发送器
    
    SpoutSDK.CreateSender

      OpenSpout()
        
        SpoutGLDXinterop.LoadGLextensions:加载NVIDIA的GL/DX扩展：加载FBO的扩展、加载FBO BLIT的扩展、加载交换链的扩展、加载PBO的扩展、找出编译和运行时是否支持bgra的扩展（未测试完）、加载wgl interop的扩展（不需要用来内存共享）



SpoutReceiver:接收器
