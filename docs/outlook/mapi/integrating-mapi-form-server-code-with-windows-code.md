---
title: 将 MAPI 表单服务器代码与 Windows 代码集成
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 47ec3e97-ad2b-43ea-842a-b2a0675eef48
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b37ae47e40906342aeecf179848311556a7d4ba4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573990"
---
# <a name="integrating-mapi-form-server-code-with-windows-code"></a>将 MAPI 表单服务器代码与 Windows 代码集成

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
记住，表单服务器是 Win32 应用程序。 因此，有一些与加载到内存中窗体服务器和完全退出相关的任务。 类似于所有 Windows 应用程序，您窗体的服务器的入口点是**WinMain**函数。 此函数为适当的位置，以执行以下任务： 
  
- 创建并注册 window 类，以便您窗体的服务器可以与其他 OLE 组件交互。
    
- 创建并注册 window 类或表单对象的用户界面的类。
    
- 调用[MAPIInitialize](mapiinitialize.md)函数。 **MAPIInitialize**处理所需的 OLE 的初始化，以及。 必须进行这一次，每个窗体服务器的实例。 
    
- 全局 atom 注册窗体服务器的类标识符 (CLSID) 的字符串表示形式。 此 atom 应存在的生存期内的窗体服务器。
    
- 调用 OLE 函数[CoRegisterClassObject](http://msdn.microsoft.com/en-us/library/ms693407.aspx)与 OLE 中注册窗体服务器的类工厂。 
    
- 创建主窗口中接收邮件。 此窗口可能不必是可见的因为用户将与单个窗体对象关联的特定 windows 进行交互。 但是，在开发期间，主窗口中可以是用于调试输出或窗体服务器的控制方便的位置。
    
- 创建窗体服务器的生存期内运行的邮件循环、 转换和 windows 将消息调度至活动窗体对象。
    
当窗体服务器退出时，应执行以下任务：
  
- 调用 OLE 函数[CoRevokeClassObject](http://msdn.microsoft.com/en-us/library/ms688650%28VS.85%29.aspx)要取消您的邮件类的 OLE 注册。 
    
- 调用**MAPIUninitialize**正确关闭到 MAPI 表单服务器的连接。 
    
- 删除全局 atom 包含的类标识符的字符串表示形式。
    
## <a name="see-also"></a>另请参阅



[编写表单服务器代码](writing-form-server-code.md)

