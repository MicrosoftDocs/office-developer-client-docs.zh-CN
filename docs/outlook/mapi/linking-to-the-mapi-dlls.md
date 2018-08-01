---
title: 链接到 MAPI DLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19fd4678-21d3-47a6-a439-1d4959cac407
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0bce1d682057b81135d1684c40bc79e6710d4e2a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776134"
---
# <a name="linking-to-the-mapi-dlls"></a>链接到 MAPI DLL

  
  
**适用于**： Outlook 
  
MAPI 客户端可以链接到 MAPI Dll 隐式或显式使用**LoadLibrary**和**GetProcAddress**的 Windows 功能。 显式链接 MAPI Dll 的信息，请参阅[MAPI 函数的链接](how-to-link-to-mapi-functions.md)。
  
MAPI 提供了在 MAPIX 类型定义语句。H 头文件中的每个以下功能：
  
[MAPILogonEx](mapilogonex.md)
  
[MAPIUninitialize](mapiuninitialize.md)
  
[MAPIInitialize](mapiinitialize.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAdminProfiles](mapiadminprofiles.md)
  
使用这些类型定义正确如果显式链接到 MAPI Dll 调用相应的入口点。
  
服务提供商可以包含非 MAPI 功能 — 与 MAPI 完全无关的功能 — 在其 DLL 中。 如果您需要使用这些功能，请使用的 DLL 和**句**后其使用从内存中删除 DLL 之前调用**LoadLibrary** 。 因为 MAPI 不知道服务提供商 DLL 的非 MAPI 使用，则将需要时可用 DLL 无法保证。 当不再需要其服务的活动会话任何客户端，MAPI 释放服务提供商 DLL。 
  

