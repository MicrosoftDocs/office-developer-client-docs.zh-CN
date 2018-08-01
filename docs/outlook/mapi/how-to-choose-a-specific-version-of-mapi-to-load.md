---
title: 选择要加载的 MAPI 的特定版本
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 85539a7f-74b6-4267-86ea-00da2c900c34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d0bce7b3a12f259b7ac5f28219c8a92dd2200f07
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775082"
---
# <a name="choose-a-specific-version-of-mapi-to-load"></a>选择要加载的 MAPI 的特定版本

**适用于**： Outlook 
  
显式链接到的 MAPI 实现时, 必须认真地选择要加载的实现。 
  
有两种方法来显式链接到的 MAPI 实现。 
  
1. 您可以加载的 MAPI 存根库，并指定自定义 DLL 以加载并调度 MAPI 呼叫到注册表中。
    
2. 您可以实现 MAPI 客户端查找算法来查找默认邮件客户端使用 MAPI 的版本和加载它。
    
因为您可以更改要直接应用程序使用 MAPI 任何实现的[Mapi32.dll 存根注册表设置](http://msdn.microsoft.com/en-us/library/ms531218%28EXCHG.10%29.aspx)，我们建议您将应用程序使用的测试与 MAPI 实现。 下面介绍显式链接这两种的方法。 
  
## <a name="reading-from-the-registry"></a>注册表中读取

### <a name="to-read-mapi-implementation-information-from-the-registry"></a>若要从注册表中读取 MAPI 实现信息

1. 指示邮件客户端自定义的 DLL 的注册表项位于`HKLM\Software\Clients\Mail`的邮件客户端密钥。 
    
   下表介绍这些键：
    
   |**键**|**说明**|
   |:-----|:-----|
   |MSIComponentID  <br/> |Windows Installer PublishComponent 类别 ID (GUID) 标识导出简单 MAPI 或 MAPI DLL 调用。 如果设置，此密钥优先于**DLLPath**或**DLLPathEx**键。  <br/> |
   |MSIApplicationLCID  <br/> |您的应用程序的区域设置标识符 (LCID)。 第一个字符串值标识子键从`HKLM\Software`和后面的字符串值标识该项下的注册表值，包含区域设置信息。  <br/> |
   |MSIOfficeLCID  <br/> |Microsoft Office 的 Lcid。 第一个字符串值标识子键从`HKLM\Software`和后面的字符串值标识该项下的注册表值。  <br/> |
   
   获取从这些项的信息。
    
2. 传递给[FGetComponentPath](fgetcomponentpath.md)函数获取上一步骤中的值。 **FGetComponentPath**是由 MAPI 存根库 Mapistub.dll 导出的函数。 将返回自定义版本的 MAPI 的路径。 


### <a name="to-load-the-implementation-of-mapi-marked-as-default"></a>若要加载的 MAPI 实现标记为默认值

1. 读取`HKLM\Software\Clients\Mail::(default)`注册表值。 
    
2. 查找指示客户端的信息，如前面所述。
    
> [!NOTE]
> 请注意默认邮件客户程序可能不实现扩展 MAPI。 
  
#### <a name="example"></a>示例

若要实现的 Outlook 加载 MAPI，查找的注册表项下`HKLM\Software\Clients\Mail\Microsoft Outlook`并将它们传递给**FGetComponentPath**。 **FGetComponentPath**将返回 Outlook 的 MAPI 实现的路径。 
  
如果未设置**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的项，检查**DLLPathEx**注册表值。 如果注册表项设置， **FGetComponentPath**提供的 MAPI 客户端的实现的路径。 
  
## <a name="implementing-the-mapi-client-lookup-algorithm"></a>实现 MAPI 客户端查找算法

下表列出了用于查找 MAPI 的自定义实现的路径从 MFCMAPI 的四个函数：
  
|**函数**|**说明**|
|:-----|:-----|
| `GetMAPIPath` <br/> |获取 MAPI 库路径。  <br/> |
| `GetMailKey` <br/> |获取 MAPI 邮件注册表项。  <br/> |
| `GetMapiMsiIds` <br/> |获取 Windows Installer 标识符。  <br/> |
| `GetComponentPath` <br/> |获取使用[FGetComponentPath](fgetcomponentpath.md)的组件路径。  <br/> |
   
因为 MFCMAPI 加载 MAPI 的默认实现默认情况下，如果您想要使用的不同实现的 MAPI，您必须明确直接执行此操作。 这是通过使用**Session\Load MAPI**例程执行。 
  
### <a name="how-these-functions-work"></a>这些函数的工作方式

1. MFCMAPI 呼叫`GetMAPIPath`、 要加载的默认 MAPI 实现的客户端参数传递 null 值。
    
2.  `GetMAPIPath`呼叫`GetMapiMsiIds` **MSIComponentID**、 **MSIApplicationLCID**，和**MSIOfficeLCID**读取值。
    
3.  `GetMapiMsiIds`呼叫`GetMailKey`的默认邮件客户端打开注册表项。 
    
4.  `GetMapiMsiIds`使用返回的注册表句柄`GetMailKey` **MSIComponentID**、 **MSIApplicationLCID**，和**MSIOfficeLCID**查阅值。
    
5. **MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值返回到`GetMAPIPath`。  `GetMAPIPath`然后将传递给`GetComponentPath`。
    
6.  `GetComponentPath`从系统目录中加载的 MAPI 存根库 Mapi32.dll。 
    
7.  `GetComponentPath`然后从 Mapi32.dll，假定 Mapi32.dll 导出**FGetComponentPath**检索**FGetComponentPath**函数的地址。
    
8. 如果从 Mapi32.dll 失败，获取**FGetComponentPath**的地址`GetComponentPath`Mapistub.dll 从检索的地址。 
    
9.  `GetComponentPath`然后调用**FGetComponentPath**，获取 MAPI 的默认版本的路径。
    
10.  `GetMAPIPath`向呼叫方，然后将加载 MAPI 和显式链接到其[链接到 MAPI 函数](how-to-link-to-mapi-functions.md)中所述，则返回此路径。
    
> [!NOTE] 
> - 英语和非英语区域设置支持本地化的份 MAPI`GetMAPIPath`读取**MSIApplicationLCID**和**MSIOfficeLCID**子项的值。  `GetMAPIPath`然后调用**FGetComponentPath**，首先为**szQualifier**，指定**MSIApplicationLCID**和再次指定**szQualifier** **MSIOfficeLCID** 。 支持非英语语言的邮件客户端的注册表项的详细信息，请参阅[设置 Up MSI 的快捷键 Your MAPI DLL](http://msdn.microsoft.com/en-us/library/ee909494%28VS.85%29.aspx)。   
> - 如果 MFCMAPI 不会收到 MAPI 使用路径`GetMAPIPath`，它从系统目录加载 MAPI 存根库。
> - 使用 MAPI 存根库，则仅适用于[显式映射 MAPI 调用对 MAPI Dll](http://msdn.microsoft.com/en-us/library/ee909490%28VS.85%29.aspx)中讨论的**MSMapiApps**注册表值。 应用程序加载特定实施的 MAPI 或加载默认实现不必设置**MSMapiApps**注册表项。 
    
## <a name="see-also"></a>另请参阅

- [FGetComponentPath](fgetcomponentpath.md)
- [MAPI 编程概述](mapi-programming-overview.md)
- [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)
- [Mapi32.dll 存根注册表设置](http://msdn.microsoft.com/en-us/library/ms531218%28EXCHG.10%29.aspx)
- [MAPI dll 设置 MSI 键](http://msdn.microsoft.com/en-us/library/ee909494%28VS.85%29.aspx)
- [显式映射到 MAPI Dll 的 MAPI 调用](http://msdn.microsoft.com/en-us/library/ee909490%28VS.85%29.aspx)

