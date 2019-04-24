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
  
请记住, 您的表单服务器是 Win32 应用程序。 因此, 存在一些与将表单服务器加载到内存中并完全退出相关的任务。 与所有 Windows 应用程序一样, 表单服务器的入口点是**WinMain**函数。 此函数是执行以下任务的适当位置: 
  
- 创建并注册一个 window 类, 以便您的表单服务器可以与其他 OLE 组件进行交互。
    
- 为表单对象的用户界面创建和注册一个窗口类或类。
    
- 调用[MAPIInitialize](mapiinitialize.md)函数。 **MAPIInitialize**也为您处理所需的 OLE 初始化。 必须为每个表单服务器实例执行一次此操作。 
    
- 使用表单服务器的类标识符 (CLSID) 的字符串表示形式注册全局 atom。 此 atom 应存在于表单服务器的生存期中。
    
- 调用 ole 函数[CoRegisterClassObject](https://msdn.microsoft.com/library/ms693407.aspx)以使用 ole 注册窗体服务器的类工厂。 
    
- 创建用于接收邮件的主窗口。 此窗口可能不需要显示, 因为用户将与与各个表单对象相关联的特定窗口进行交互。 但是, 在开发过程中, 主窗口可用作调试表单服务器的输出或控制的便利位置。
    
- 创建在表单服务器的生存期内运行的邮件循环, 将 windows 消息转换并调度到活动的窗体对象。
    
当表单服务器退出时, 应执行以下任务:
  
- 调用 OLE 函数[CoRevokeClassObject](https://msdn.microsoft.com/library/ms688650%28VS.85%29.aspx)以撤消您的邮件类的 OLE 注册。 
    
- 调用**MAPIUninitialize**以正确关闭表单服务器与 MAPI 的连接。 
    
- 删除包含类标识符的字符串表示形式的全局 atom。
    
## <a name="see-also"></a>另请参阅



[编写表单服务器代码](writing-form-server-code.md)

