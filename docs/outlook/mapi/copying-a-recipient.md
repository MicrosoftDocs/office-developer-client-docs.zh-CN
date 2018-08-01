---
title: 复制收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b9a41f44-4c7e-4c57-b536-63fb85e4fae6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: dd68bc2054136a7f587b05dc56dbeabd06de1f08
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774705"
---
# <a name="copying-a-recipient"></a><span data-ttu-id="c43aa-103">复制收件人</span><span class="sxs-lookup"><span data-stu-id="c43aa-103">Copying a Recipient</span></span>

  
  
<span data-ttu-id="c43aa-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c43aa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c43aa-105">若要将一个或多个收件人复制到另一个容器或相同的容器，请先检查目标容器可修改。</span><span class="sxs-lookup"><span data-stu-id="c43aa-105">To copy one or more recipients from one container into another or the same container, first check that the target container is modifiable.</span></span> <span data-ttu-id="c43aa-106">容器的可修改其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中设置 AB_MODIFIABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="c43aa-106">Containers that are modifiable set the AB_MODIFIABLE flag in their **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="c43aa-107">要复制到可修改容器的一个或多个条目，调用目标容器[IABContainer::CopyEntries](iabcontainer-copyentries.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c43aa-107">To copy one or more entries into a modifiable container, call the destination container's [IABContainer::CopyEntries](iabcontainer-copyentries.md) method.</span></span> <span data-ttu-id="c43aa-108">由于复制通讯簿条目可能耗时， **CopyEntries**接受四个输入参数： 要复制的条目、 窗口句柄、 进度指示器和标志的位掩码的项标识符的数组。</span><span class="sxs-lookup"><span data-stu-id="c43aa-108">Because copying address book entries can be time-consuming, **CopyEntries** accepts four input parameters: an array of entry identifiers for the entries to be copied, a window handle, a progress indicator, and a bitmask of flags.</span></span> 
  
<span data-ttu-id="c43aa-109">通过通讯簿提供程序使用的窗口句柄和进度指示器用于向用户显示操作的状态。</span><span class="sxs-lookup"><span data-stu-id="c43aa-109">The window handle and progress indicator are used by the address book provider to show the status of the operation to the user.</span></span> <span data-ttu-id="c43aa-110">如果您想要显示进度， _ulUIParam_参数中传递的进度指示器的父窗口的窗口句柄，并且不要_ulFlags_参数中设置 AB_NO_DIALOG 标志。</span><span class="sxs-lookup"><span data-stu-id="c43aa-110">If you want to display progress, pass a window handle for the parent window of the progress indicator in the  _ulUIParam_ parameter and do not set the AB_NO_DIALOG flag in the  _ulFlags_ parameter.</span></span> <span data-ttu-id="c43aa-111">如果您有自己的进度指示器的实现，请将指针传递给_lpProgress_参数中的实现。</span><span class="sxs-lookup"><span data-stu-id="c43aa-111">If you have your own implementation of a progress indicator, pass a pointer to the implementation in the  _lpProgress_ parameter.</span></span> <span data-ttu-id="c43aa-112">如果没有，传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="c43aa-112">If not, pass NULL.</span></span> <span data-ttu-id="c43aa-113">通讯簿提供程序将使用 MAPI 进度指示器实现。</span><span class="sxs-lookup"><span data-stu-id="c43aa-113">The address book provider will use the MAPI progress indicator implementation.</span></span> 
  
<span data-ttu-id="c43aa-114">Flags 的位掩码指示您是否想要显示进度指示器和检查应处理方式重复项。</span><span class="sxs-lookup"><span data-stu-id="c43aa-114">The bitmask of flags indicates whether or not you want to display a progress indicator and how duplicate entry checking should be handled.</span></span> <span data-ttu-id="c43aa-115">设置 AB_NO_DIALOG 标志禁止进度指示器。</span><span class="sxs-lookup"><span data-stu-id="c43aa-115">Set the AB_NO_DIALOG flag to suppress a progress indicator.</span></span> <span data-ttu-id="c43aa-116">设置 CREATE_CHECK_DUP_LOOSE 标志以指示通讯簿提供程序松散检查重复项或更严格的重复检查 CREATE_CHECK_DUP_STRICT 标记。</span><span class="sxs-lookup"><span data-stu-id="c43aa-116">Set the CREATE_CHECK_DUP_LOOSE flag to instruct the address book provider to loosely check for duplicates or the CREATE_CHECK_DUP_STRICT flag for stricter duplicate checking.</span></span> <span data-ttu-id="c43aa-117">提供程序确定有重复项时，设置要复制条目的 CREATE_REPLACE 标志会替换现有条目。</span><span class="sxs-lookup"><span data-stu-id="c43aa-117">Set the CREATE_REPLACE flag to have copied entries replace existing entries when the provider determines there are duplicates.</span></span> 
  
<span data-ttu-id="c43aa-118">在复制到个人通讯簿 (PAB) 的容器，提供程序复制部分或全部为每个项的属性。</span><span class="sxs-lookup"><span data-stu-id="c43aa-118">When copying into a personal address book (PAB) container, the provider copies some or all of the properties for each entry.</span></span> <span data-ttu-id="c43aa-119">MAPI 无法建立实现容器复制操作的提供程序的要求，因为您无法进行假设数量和类型使用的通讯簿条目复制的属性。</span><span class="sxs-lookup"><span data-stu-id="c43aa-119">Because MAPI does not establish requirements for providers implementing container copy operations, you cannot make assumptions about the number and type of properties that are copied with an address book entry.</span></span>
  

