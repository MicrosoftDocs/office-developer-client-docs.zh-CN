---
title: 将 MAPI 表单服务器代码与 Windows 代码集成
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 47ec3e97-ad2b-43ea-842a-b2a0675eef48
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 33b205c0ac5caf5fc049a0732cd219aa2c321326
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332177"
---
# <a name="integrating-mapi-form-server-code-with-windows-code"></a>将 MAPI 表单服务器代码与 Windows 代码集成

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
回想一下，您的表单服务器是 Win32 应用程序。 因此，有些任务与将表单服务器加载到内存中并完全退出有关。 与Windows一样，表单服务器的入口点是 **WinMain** 函数。 此函数是执行以下任务的适当位置： 
  
- 创建和注册窗口类，以便表单服务器可以与其他 OLE 组件交互。
    
- 为表单对象的用户界面创建和注册窗口类。
    
- 调用 [MAPIInitialize](mapiinitialize.md) 函数。 **MAPIInitialize** 也处理所需的 OLE 初始化。 每个表单服务器实例必须完成一次此操作。 
    
- 使用表单服务器的类标识符的字符串表示形式注册全局 atom (CLSID) 。 此 atom 应在窗体服务器的生命周期内存在。
    
- 调用 OLE 函数 [CoRegisterClassObject](https://msdn.microsoft.com/library/ms693407.aspx) 以使用 OLE 注册表单服务器的类工厂。 
    
- 创建主窗口以接收邮件。 此窗口可能不需要可见，因为用户将与与单个表单对象关联的特定窗口交互。 但是，在开发过程中，主窗口可以是调试表单服务器的输出或控制的方便位置。
    
- 创建在窗体服务器生存期内运行的消息循环，将窗口消息转换和调度到活动窗体对象。
    
当表单服务器退出时，它应执行以下任务：
  
- 调用 OLE 函数 [CoRevokeClassObject](https://msdn.microsoft.com/library/ms688650%28VS.85%29.aspx) 以撤消邮件类的 OLE 注册。 
    
- 调用 **MAPIUninitialize** 以正确关闭表单服务器与 MAPI 的连接。 
    
- 删除包含类标识符的字符串表示的全局 atom。
    
## <a name="see-also"></a>另请参阅



[编写表单服务器代码](writing-form-server-code.md)

