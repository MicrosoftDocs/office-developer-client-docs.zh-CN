---
title: 复制收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b9a41f44-4c7e-4c57-b536-63fb85e4fae6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3a4fb1a3f76481bf1960c251a33911b871a8791c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419084"
---
# <a name="copying-a-recipient"></a><span data-ttu-id="949ea-103">复制收件人</span><span class="sxs-lookup"><span data-stu-id="949ea-103">Copying a Recipient</span></span>

  
  
<span data-ttu-id="949ea-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="949ea-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="949ea-105">若要将一个或多个收件人从一个容器复制到另一个容器或同一容器, 请首先检查目标容器是否可修改。</span><span class="sxs-lookup"><span data-stu-id="949ea-105">To copy one or more recipients from one container into another or the same container, first check that the target container is modifiable.</span></span> <span data-ttu-id="949ea-106">可修改的容器在其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置 AB_MODIFIABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="949ea-106">Containers that are modifiable set the AB_MODIFIABLE flag in their **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="949ea-107">若要将一个或多个条目复制到可修改的容器中, 请调用目标容器的[IABContainer:: CopyEntries](iabcontainer-copyentries.md)方法。</span><span class="sxs-lookup"><span data-stu-id="949ea-107">To copy one or more entries into a modifiable container, call the destination container's [IABContainer::CopyEntries](iabcontainer-copyentries.md) method.</span></span> <span data-ttu-id="949ea-108">由于复制通讯簿条目可能非常耗时, **CopyEntries**接受四个输入参数: 一个用于要复制的条目的条目标识符数组、一个窗口句柄、一个进度指示器和一个标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="949ea-108">Because copying address book entries can be time-consuming, **CopyEntries** accepts four input parameters: an array of entry identifiers for the entries to be copied, a window handle, a progress indicator, and a bitmask of flags.</span></span> 
  
<span data-ttu-id="949ea-109">通讯簿提供程序使用窗口句柄和进度指示器向用户显示操作的状态。</span><span class="sxs-lookup"><span data-stu-id="949ea-109">The window handle and progress indicator are used by the address book provider to show the status of the operation to the user.</span></span> <span data-ttu-id="949ea-110">如果要显示进度, 请在_ulUIParam_参数中为进度指示器的父窗口传递窗口句柄, 不要在_ulFlags_参数中设置 AB_NO_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="949ea-110">If you want to display progress, pass a window handle for the parent window of the progress indicator in the  _ulUIParam_ parameter and do not set the AB_NO_DIALOG flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="949ea-111">如果你有自己的进度指示器实现, 请在_lpProgress_参数中传递指向实现的指针。</span><span class="sxs-lookup"><span data-stu-id="949ea-111">If you have your own implementation of a progress indicator, pass a pointer to the implementation in the  _lpProgress_ parameter.</span></span> <span data-ttu-id="949ea-112">如果不是, 则传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="949ea-112">If not, pass NULL.</span></span> <span data-ttu-id="949ea-113">通讯簿提供程序将使用 MAPI 进度指示器实现。</span><span class="sxs-lookup"><span data-stu-id="949ea-113">The address book provider will use the MAPI progress indicator implementation.</span></span> 
  
<span data-ttu-id="949ea-114">flags 的位掩码指示是否要显示进度指示器以及应如何处理重复项检查。</span><span class="sxs-lookup"><span data-stu-id="949ea-114">The bitmask of flags indicates whether or not you want to display a progress indicator and how duplicate entry checking should be handled.</span></span> <span data-ttu-id="949ea-115">设置 AB_NO_DIALOG 标志以禁止显示进度指示器。</span><span class="sxs-lookup"><span data-stu-id="949ea-115">Set the AB_NO_DIALOG flag to suppress a progress indicator.</span></span> <span data-ttu-id="949ea-116">设置 CREATE_CHECK_DUP_LOOSE 标志以指示通讯簿提供程序对重复项或 CREATE_CHECK_DUP_STRICT 标志进行松散检查以进行更严格的重复检查。</span><span class="sxs-lookup"><span data-stu-id="949ea-116">Set the CREATE_CHECK_DUP_LOOSE flag to instruct the address book provider to loosely check for duplicates or the CREATE_CHECK_DUP_STRICT flag for stricter duplicate checking.</span></span> <span data-ttu-id="949ea-117">将 CREATE_REPLACE 标志设置为当提供程序确定存在重复项时, 已复制的条目将替换现有的条目。</span><span class="sxs-lookup"><span data-stu-id="949ea-117">Set the CREATE_REPLACE flag to have copied entries replace existing entries when the provider determines there are duplicates.</span></span> 
  
<span data-ttu-id="949ea-118">当复制到个人通讯簿 (PAB) 容器中时, 提供程序将复制每个条目的部分或全部属性。</span><span class="sxs-lookup"><span data-stu-id="949ea-118">When copying into a personal address book (PAB) container, the provider copies some or all of the properties for each entry.</span></span> <span data-ttu-id="949ea-119">由于 MAPI 不会为实现容器复制操作的提供程序建立要求, 因此无法假设与通讯簿条目一起复制的属性的数量和类型。</span><span class="sxs-lookup"><span data-stu-id="949ea-119">Because MAPI does not establish requirements for providers implementing container copy operations, you cannot make assumptions about the number and type of properties that are copied with an address book entry.</span></span>
  

