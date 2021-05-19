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
  
当显式链接到 MAPI 的实现时，必须仔细选择要加载的实现。 
  
有两种方法可显式链接到 MAPI 的实现。 
  
1. 可以加载 MAPI 存根库，在注册表中指定要加载和调度 MAPI 调用的自定义 DLL。
    
2. 您可以实现 MAPI 客户端查找算法来查找默认邮件客户端使用的 MAPI 版本并加载它。
    
由于可以更改Mapi32.dll[存根注册表 设置](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx)以指示应用程序使用 MAPI 的任何实现，因此我们建议你指示应用程序使用已测试的 MAPI 实现。 下面介绍了两种显式链接方法。 
  
## <a name="reading-from-the-registry"></a>从注册表读取

### <a name="to-read-mapi-implementation-information-from-the-registry"></a>从注册表中读取 MAPI 实现信息

1. 指示邮件客户端的自定义 DLL 的注册表项位于邮件客户端  `HKLM\Software\Clients\Mail` 的项下。 
    
   下表介绍了这些键：
    
   |**按键**|**描述**|
   |:-----|:-----|
   |MSIComponentID  <br/> |一Windows Installer PublishComponent 类别 ID (GUID) ，用于标识导出简单 MAPI 或 MAPI 调用的 DLL。 如果设置，则此键优先于 **DLLPath** 或 **DLLPathEx** 键。  <br/> |
   |MSIApplicationLCID  <br/> |应用程序 (LCID) 区域设置标识符。 第一个字符串值标识来自 的子项，后续字符串值标识此注册表项下包含区域设置信息的  `HKLM\Software` 注册表值。  <br/> |
   |MSIOfficeLCID  <br/> |Microsoft Office 的 CID。 第一个字符串值标识来自 的子项，后续  `HKLM\Software` 字符串值标识此注册表项下的注册表值。  <br/> |
   
   从这些密钥获取信息。
    
2. 将上一步获取的值传递到 [FGetComponentPath](fgetcomponentpath.md) 函数。 **FGetComponentPath** 是由 MAPI 存根库导出的函数Mapistub.dll。 它返回 MAPI 的自定义版本的路径。 


### <a name="to-load-the-implementation-of-mapi-marked-as-default"></a>加载标记为默认值的 MAPI 的实现

1. 读取  `HKLM\Software\Clients\Mail::(default)` 注册表值。 
    
2. 如前文所述，查找指示的客户端的信息。
    
> [!NOTE]
> 请注意，默认邮件客户端可能不会实现扩展 MAPI。 
  
#### <a name="example"></a>示例

若要加载 MAPI（由 Outlook 实现，请查找 下的注册表项，然后将它们传递到 `HKLM\Software\Clients\Mail\Microsoft Outlook` **FGetComponentPath**。 **FGetComponentPath** 将返回 mapI Outlook实现的路径。 
  
如果未设置 **项 MSIComponentID、MSIApplicationLCID** 和 **MSIOfficeLCID，** 请检查 **DLLPathEx** 注册表值。  如果设置了这些键， **则 FGetComponentPath** 会提供客户端实现 MAPI 的路径。 
  
## <a name="implementing-the-mapi-client-lookup-algorithm"></a>实现 MAPI 客户端查找算法

下表列出了 MFCMAPI 中用于查找 MAPI 自定义实现路径的四个函数：
  
|**函数**|**说明**|
|:-----|:-----|
| `GetMAPIPath` <br/> |获取 MAPI 库路径。  <br/> |
| `GetMailKey` <br/> |获取 MAPI 邮件注册表项。  <br/> |
| `GetMapiMsiIds` <br/> |获取 Windows Installer 标识符。  <br/> |
| `GetComponentPath` <br/> |使用 [FGetComponentPath 获取组件路径](fgetcomponentpath.md)。  <br/> |
   
由于 MFCMAPI 默认加载 MAPI 的默认实现，因此如果要使用不同的 MAPI 实现，则必须明确指示它这样做。 这是通过使用 **Session\Load MAPI** 例程执行的。 
  
### <a name="how-these-functions-work"></a>这些函数如何工作

1. MFCMAPI  `GetMAPIPath` 调用 ，为客户端参数传递 NULL，以加载默认的 MAPI 实现。
    
2.  `GetMAPIPath`调用 `GetMapiMsiIds` 以读取 **MSIComponentID、MSIApplicationLCID** 和 **MSIOfficeLCID 的值**。 
    
3.  `GetMapiMsiIds` 调用  `GetMailKey` 打开默认邮件客户端的注册表项。 
    
4.  `GetMapiMsiIds` 使用 返回的注册表句柄查找  `GetMailKey` **MSIComponentID** **、MSIApplicationLCID** 和 **MSIOfficeLCID 的值**。
    
5. **MSIComponentID、MSIApplicationLCID** 和 **MSIOfficeLCID** 的值将返回到 `GetMAPIPath` 。  `GetMAPIPath` 然后将它们传递给  `GetComponentPath` 。
    
6.  `GetComponentPath` 从系统目录加载 MAPI 存根库Mapi32.dll，并加载该存根库。 
    
7.  `GetComponentPath` 然后，从数据库检索 **FGetComponentPath** 函数的地址Mapi32.dll假定Mapi32.dll **导出 FGetComponentPath**。
    
8. 如果从服务器获取 **FGetComponentPath** Mapi32.dll失败，请从  `GetComponentPath` Mapistub.dll。 
    
9.  `GetComponentPath` 然后调用 **FGetComponentPath**，获取 MAPI 的默认版本的路径。
    
10.  `GetMAPIPath` 然后将此路径返回到调用方，调用方随后加载 MAPI 并显式链接到它，如 [链接到 MAPI 函数 中所述](how-to-link-to-mapi-functions.md)。
    
> [!NOTE] 
> - 若要支持针对英语和非英语区域设置本地化的 MAPI 副本，请读取  `GetMAPIPath` **MSIApplicationLCID** 和 **MSIOfficeLCID** 子项的值。  `GetMAPIPath` 然后调用 **FGetComponentPath**，首先将 **MSIApplicationLCID** 指定为 **szQualifier**，然后再次将 **MSIOfficeLCID** 指定为 **szQualifier**。 有关支持非英语语言的邮件客户端的注册表项详细信息，请参阅 Setting Up [the MSI Keys for Your MAPI DLL。](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)   
> - 如果 MFCMAPI 没有收到使用 的 MAPI 的路径，它将从系统目录加载 MAPI 存根  `GetMAPIPath` 库。
> - 明确将 MAPI 调用映射到 [MAPI DLL](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)中讨论的 **MSMapiApps** 注册表值仅适用于使用 MAPI 存根库的情况。 加载 MAPI 的特定实现或加载默认实现的应用程序不需要设置 **MSMapiApps** 注册表项。 
    
## <a name="see-also"></a>另请参阅

- [FGetComponentPath](fgetcomponentpath.md)
- [MAPI 编程概述](mapi-programming-overview.md)
- [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)
- [Mapi32.dll存根注册表设置](https://msdn.microsoft.com/library/ms531218%28EXCHG.10%29.aspx)
- [为 MAPI DLL 设置 MSI 密钥](https://msdn.microsoft.com/library/ee909494%28VS.85%29.aspx)
- [将 MAPI 调用显式映射到 MAPI DLL](https://msdn.microsoft.com/library/ee909490%28VS.85%29.aspx)

