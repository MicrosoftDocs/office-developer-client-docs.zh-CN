---
title: 打开在通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79e0bc93-f37d-4f6a-beed-7519d01e0056
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4b9d7b8cf71b4e00dac6022e1dda727ef7a23036
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776553"
---
# <a name="opening-the-address-book"></a><span data-ttu-id="bfd00-103">打开在通讯簿</span><span class="sxs-lookup"><span data-stu-id="bfd00-103">Opening the address book</span></span>

<span data-ttu-id="bfd00-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bfd00-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bfd00-105">调用[IMAPISession::OpenAddressBook](imapisession-openaddressbook.md)打开集成的通讯簿和检索指向 MAPI [IAddrBook: IMAPIProp](iaddrbookimapiprop.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bfd00-105">Call [IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) to open the integrated address book and retrieve a pointer to the MAPI [IAddrBook : IMAPIProp](iaddrbookimapiprop.md) interface.</span></span> <span data-ttu-id="bfd00-106">**IAddrBook**接口的方法可用于访问所有的配置文件中的地址簿提供程序的每个容器中的条目。</span><span class="sxs-lookup"><span data-stu-id="bfd00-106">The methods of the **IAddrBook** interface can be used to access entries in all of the containers of each of the address book providers in the profile.</span></span> 
  
<span data-ttu-id="bfd00-107">**OpenAddressBook**可能返回警告，MAPI_W_ERRORS_RETURNED，以指示时出现问题与一个或多个地址簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="bfd00-107">**OpenAddressBook** might return a warning, MAPI_W_ERRORS_RETURNED, to indicate that there were problems with one or more of the address book providers.</span></span> <span data-ttu-id="bfd00-108">交互式客户端应调用[IMAPISession::GetLastError](imapisession-getlasterror.md)检索其他错误信息并显示呼叫**OpenAddressBook**返回的信息第一个时间，并返回一条警告。</span><span class="sxs-lookup"><span data-stu-id="bfd00-108">Interactive clients should call [IMAPISession::GetLastError](imapisession-getlasterror.md) to retrieve additional error information and display the returned information the first time they call **OpenAddressBook** and it returns a warning.</span></span> 
  
<span data-ttu-id="bfd00-109">非交互式客户端应忽略的警告，并继续如同方法成功。</span><span class="sxs-lookup"><span data-stu-id="bfd00-109">Noninteractive clients should ignore the warning and proceed as if the method succeeded.</span></span> <span data-ttu-id="bfd00-110">返回的**IAddrBook**接口是有效无论是否所有，一些，或无配置文件中的地址簿提供程序正在运行。</span><span class="sxs-lookup"><span data-stu-id="bfd00-110">The returned **IAddrBook** interface is valid regardless of whether all, some, or none of the address book providers in the profile are running.</span></span> <span data-ttu-id="bfd00-111">因此，交互式和非交互式客户端必须始终记住要在会话结束时释放**IAddrBook**指针。</span><span class="sxs-lookup"><span data-stu-id="bfd00-111">Therefore, both interactive and noninteractive clients must always remember to release the **IAddrBook** pointer when the session ends.</span></span> 
  

