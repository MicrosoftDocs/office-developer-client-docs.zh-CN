---
title: 打开通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79e0bc93-f37d-4f6a-beed-7519d01e0056
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6d1a7e8e1d9debd7eb715bbe4958657c000f1e6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404545"
---
# <a name="opening-the-address-book"></a><span data-ttu-id="4fc9d-103">打开通讯簿</span><span class="sxs-lookup"><span data-stu-id="4fc9d-103">Opening the address book</span></span>

<span data-ttu-id="4fc9d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4fc9d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4fc9d-105">调用 [IMAPISession：：OpenAddressBook](imapisession-openaddressbook.md) 以打开集成通讯簿并检索到 MAPI [IAddrBook ： IMAPIProp 接口的](iaddrbookimapiprop.md) 指针。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-105">Call [IMAPISession::OpenAddressBook](imapisession-openaddressbook.md) to open the integrated address book and retrieve a pointer to the MAPI [IAddrBook : IMAPIProp](iaddrbookimapiprop.md) interface.</span></span> <span data-ttu-id="4fc9d-106">**IAddrBook** 接口的方法可用于访问配置文件中每个通讯簿提供程序的所有容器中的条目。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-106">The methods of the **IAddrBook** interface can be used to access entries in all of the containers of each of the address book providers in the profile.</span></span> 
  
<span data-ttu-id="4fc9d-107">**OpenAddressBook** 可能会返回警告MAPI_W_ERRORS_RETURNED，以指示一个或多个通讯簿提供程序出现问题。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-107">**OpenAddressBook** might return a warning, MAPI_W_ERRORS_RETURNED, to indicate that there were problems with one or more of the address book providers.</span></span> <span data-ttu-id="4fc9d-108">交互式客户端应调用 [IMAPISession：：GetLastError](imapisession-getlasterror.md) 以检索其他错误信息，并首次调用 **OpenAddressBook** 时显示返回的信息，并返回警告。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-108">Interactive clients should call [IMAPISession::GetLastError](imapisession-getlasterror.md) to retrieve additional error information and display the returned information the first time they call **OpenAddressBook** and it returns a warning.</span></span> 
  
<span data-ttu-id="4fc9d-109">非交互客户端应忽略警告并继续操作，就像方法成功一样。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-109">Noninteractive clients should ignore the warning and proceed as if the method succeeded.</span></span> <span data-ttu-id="4fc9d-110">返回 **的 IAddrBook** 接口有效，无论配置文件中是否正在运行所有、部分或没有任何通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-110">The returned **IAddrBook** interface is valid regardless of whether all, some, or none of the address book providers in the profile are running.</span></span> <span data-ttu-id="4fc9d-111">因此，交互和非交互客户端必须始终记住在会话结束时释放 **IAddrBook** 指针。</span><span class="sxs-lookup"><span data-stu-id="4fc9d-111">Therefore, both interactive and noninteractive clients must always remember to release the **IAddrBook** pointer when the session ends.</span></span> 
  

