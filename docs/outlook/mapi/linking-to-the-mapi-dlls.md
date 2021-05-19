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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419301"
---
# <a name="linking-to-the-mapi-dlls"></a>链接到 MAPI DLL

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 客户端可以隐式或显式链接到 MAPI DLL，或者使用 Windows 函数 **LoadLibrary** 和 **GetProcAddress** 显式链接。 有关显式链接 MAPI DLL 的信息，请参阅 [链接到 MAPI 函数](how-to-link-to-mapi-functions.md)。
  
MAPI 在 MAPIX 中提供类型定义语句。以下每个函数的 H 头文件：
  
[MAPILogonEx](mapilogonex.md)
  
[MAPIUninitialize](mapiuninitialize.md)
  
[MAPIInitialize](mapiinitialize.md)
  
[MAPIAllocateBuffer](mapiallocatebuffer.md)
  
[MAPIAllocateMore](mapiallocatemore.md)
  
[MAPIFreeBuffer](mapifreebuffer.md)
  
[MAPIAdminProfiles](mapiadminprofiles.md)
  
如果显式链接到 MAPI DLL，请使用这些类型定义正确调用相应的入口点。
  
服务提供程序可以在其 DLL 中包含非 MAPI 功能（与 MAPI 完全无关的功能）。 如果你需要使用这些功能，在使用 DLL 和 FreeLibrary 之前调用 **LoadLibrary，** 以在使用 DLL 后从内存中删除该 DLL。  由于 MAPI 不知道服务提供程序 DLL 的非 MAPI 用法，因此无法保证 DLL 将根据需要可用。 当不再有任何具有活动会话的客户端需要其服务时，MAPI 将释放服务提供程序 DLL。 
  

