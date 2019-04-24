---
title: 选择要加载的特定版本 MAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 85539a7f-74b6-4267-86ea-00da2c900c34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d353eba55e33b8ab48b3c47d2f31f1b5e0973b58
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344518"
---
# <a name="choose-a-specific-version-of-mapi-to-load"></a>选择要加载的特定版本 MAPI

**适用于**：Outlook 2013 | Outlook 2016 
  
当显式链接到 MAPI 的实现时, 您必须仔细选择要加载的实现。 
  
有两种方法可显式链接到 MAPI 的实现。 
  
1. 您可以加载 mapi 存根库, 并在注册表中指定一个用于加载和调度 MAPI 调用的自定义 DLL。
    
2. 您可以实现 MAPI 客户端查找算法, 以查找默认邮件客户端使用的 mapi 版本并加载它。
    
由于您可以更改[Mapi32 存根 (Stub) 注册表设置](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx), 以使应用程序使用任何 mapi 实现, 因此我们建议您将应用程序定向到使用已通过测试的 mapi 实现。 下面介绍了这两种方法的显式链接。 
  
## <a name="reading-from-the-registry"></a>读取注册表

### <a name="to-read-mapi-implementation-information-from-the-registry"></a>从注册表中读取 MAPI 实现信息

1. 指示邮件客户端的自定义 DLL 的注册表项位于邮件客户端的`HKLM\Software\Clients\Mail`键下。 
    
   下表对这些项进行了描述:
    
   |**按键**|**描述**|
   |:-----|:-----|
   |MSIComponentID  <br/> |Windows Installer PublishComponent 类别 ID (GUID), 用于标识导出简单 MAPI 或 mapi 调用的 DLL。 如果设置, 则此项优先于**DLLPath**或**DLLPathEx**项。  <br/> |
   |MSIApplicationLCID  <br/> |应用程序的区域设置标识符 (LCID)。 第一个字符串值标识 from `HKLM\Software`关键字 and 后续字符串值标识此项下包含区域设置信息的注册表值。  <br/> |
   |MSIOfficeLCID  <br/> |Microsoft Office 的 lcid。 第一个字符串值标识 from `HKLM\Software`关键字, 后面的字符串值标识此项下的注册表值。  <br/> |
   
   获取这些项中的信息。
    
2. 将您从上一步获取的值传递给[FGetComponentPath](fgetcomponentpath.md)函数。 **FGetComponentPath**是由 MAPI 存根库 Mapistub 导出的函数。 它返回 MAPI 自定义版本的路径。 


### <a name="to-load-the-implementation-of-mapi-marked-as-default"></a>加载标记为默认值的 MAPI 的实现

1. 读取`HKLM\Software\Clients\Mail::(default)`注册表值。 
    
2. 如上文所述, 查找指示的客户端的信息。
    
> [!NOTE]
> 请注意, 默认邮件客户端可能不会实现扩展 MAPI。 
  
#### <a name="example"></a>示例

若要加载 Outlook 实现的 MAPI, 请在下面`HKLM\Software\Clients\Mail\Microsoft Outlook`查找注册表项, 并将其传递给**FGetComponentPath**。 **FGetComponentPath**将返回 Outlook 的 MAPI 实现的路径。 
  
如果未设置 keys **MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID** , 请检查**DLLPathEx**注册表值。 如果设置了这些项, **FGetComponentPath**将提供客户端的 MAPI 实现的路径。 
  
## <a name="implementing-the-mapi-client-lookup-algorithm"></a>实现 MAPI 客户端查找算法

下表列出了 MFCMAPI 中的四个函数, 这些函数用于查找 MAPI 的自定义实现的路径:
  
|**函数**|**说明**|
|:-----|:-----|
| `GetMAPIPath` <br/> |获取 MAPI 库路径。  <br/> |
| `GetMailKey` <br/> |获取 MAPI 邮件注册表项。  <br/> |
| `GetMapiMsiIds` <br/> |获取 Windows Installer 标识符。  <br/> |
| `GetComponentPath` <br/> |使用[FGetComponentPath](fgetcomponentpath.md)获取组件路径。  <br/> |
   
由于默认情况下, MFCMAPI 会加载默认的 mapi 实现, 因此, 如果要使用不同的 mapi 实现, 则必须显式指导它执行此操作。 这是通过使用**Session\Load MAPI**例程来执行的。 
  
### <a name="how-these-functions-work"></a>这些函数的工作原理

1. MFCMAPI 调用`GetMAPIPath`, 为客户端参数传递 NULL, 以加载默认的 MAPI 实现。
    
2.  `GetMAPIPath`调用`GetMapiMsiIds`以读取**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值。
    
3.  `GetMapiMsiIds`调用`GetMailKey`以打开默认邮件客户端的注册表项。 
    
4.  `GetMapiMsiIds`使用`GetMailKey`返回的注册表句柄查找**MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值。
    
5. **MSIComponentID**、 **MSIApplicationLCID**和**MSIOfficeLCID**的值将返回到`GetMAPIPath`。  `GetMAPIPath`然后将其传递`GetComponentPath`给。
    
6.  `GetComponentPath`从系统目录中加载 MAPI 存根库 Mapi32。 
    
7.  `GetComponentPath`然后, 从 Mapi32 中检索**FGetComponentPath**函数的地址, 假定 Mapi32 导出**FGetComponentPath**。
    
8. 如果从 Mapi32 获取**FGetComponentPath**的地址失败, `GetComponentPath`则从 Mapistub 检索地址。 
    
9.  `GetComponentPath`然后, 调用**FGetComponentPath**, 获取默认的 MAPI 版本的路径。
    
10.  `GetMAPIPath`然后, 将此路径返回给调用方, 然后加载 mapi 并显式链接到它, 如[链接到 MAPI 函数](how-to-link-to-mapi-functions.md)中所述。
    
> [!NOTE] 
> - 若要支持适用于英语和非英语区域设置的 MAPI 的`GetMAPIPath`本地化副本, 请阅读**MSIApplicationLCID**和**MSIOfficeLCID**子项的值。  `GetMAPIPath`然后调用**FGetComponentPath**, 首先将**MSIApplicationLCID**指定为**szQualifier**, 并再次将**MSIOfficeLCID**指定为**szQualifier**。 有关支持非英语语言的邮件客户端的注册表项的详细信息, 请参阅[设置 MAPI DLL 的 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)。   
> - 如果 MFCMAPI 没有收到使用`GetMAPIPath`mapi 的路径, 它将从系统目录加载 mapi 存根库。
> - 仅当使用 mapi 存根库时, 在[显式将 mapi 调用映射到 mapi dll](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)时所讨论的**MSMapiApps**注册表值才适用。 加载特定的 MAPI 实现或加载默认实现的应用程序不需要设置**MSMapiApps**注册表项。 
    
## <a name="see-also"></a>另请参阅

- [FGetComponentPath](fgetcomponentpath.md)
- [MAPI 编程概述](mapi-programming-overview.md)
- [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)
- [Mapi32 存根注册表设置](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx)
- [为 MAPI DLL 设置 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)
- [将 mapi 调用显式映射到 mapi dll](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)

