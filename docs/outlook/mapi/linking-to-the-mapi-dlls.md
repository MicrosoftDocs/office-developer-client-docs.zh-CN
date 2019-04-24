---
title: 链接到 MAPI DLL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 19fd4678-21d3-47a6-a439-1d4959cac407
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 394537a60f4cb9603024115ccea67570291d8ac6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270040"
---
# <a name="linking-to-the-mapi-dlls"></a>链接到 MAPI DLL

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
mapi 客户端可以隐式链接到 mapi dll, 也可以通过使用 Windows 函数**LoadLibrary**和**GetProcAddress**进行显式链接。 有关显式链接 MAPI dll 的信息, 请参阅[链接到 mapi 函数](how-to-link-to-mapi-functions.md)。
  
MAPI 在 MAPIX 中提供类型定义语句。以下每个函数的 H 头文件:
  
[MAPILogonEx](mapilogonex.md)
  
[MAPIUninitialize](mapiuninitialize.md)
  
[MAPIInitialize](mapiinitialize.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAdminProfiles](mapiadminprofiles.md)
  
如果显式链接到 MAPI dll, 请使用这些类型定义来正确地调用相应的入口点。
  
服务提供程序可以在其 DLL 中包含非 mapi 功能 (与 MAPI 完全无关的功能)。 如果需要使用这些功能, 请在使用 dll 和**FreeLibrary**之前调用**LoadLibrary** , 以在使用 dll 后将其从内存中删除。 由于 MAPI 不知道服务提供程序 DLL 的非 MAPI 使用, 因此不能保证 DLL 在需要时可用。 当不再有任何具有需要服务的活动会话的客户端时, MAPI 将释放服务提供程序 DLL。 
  

