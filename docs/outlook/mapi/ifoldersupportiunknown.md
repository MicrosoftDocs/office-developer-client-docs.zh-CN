---
title: IFolderSupport IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IFolderSupport
api_type:
- COM
ms.assetid: a4b03a66-cf6d-cd20-f1df-b247d3ee87aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d17de9cc11bd791c75b83093a0431c138fd606d6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564169"
---
# <a name="ifoldersupport--iunknown"></a><span data-ttu-id="02c89-103">IFolderSupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="02c89-103">IFolderSupport : IUnknown</span></span>

  
  
<span data-ttu-id="02c89-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="02c89-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="02c89-105">提供的共享文件夹的支持的信息。</span><span class="sxs-lookup"><span data-stu-id="02c89-105">Provides information about a folder's support for sharing.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="02c89-106">提供者：</span><span class="sxs-lookup"><span data-stu-id="02c89-106">Provided by:</span></span>  <br/> |<span data-ttu-id="02c89-107">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="02c89-107">Message store provider</span></span>  <br/> |
|<span data-ttu-id="02c89-108">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="02c89-108">Interface identifier:</span></span>  <br/> |<span data-ttu-id="02c89-109">IID_IFolderSupport</span><span class="sxs-lookup"><span data-stu-id="02c89-109">IID_IFolderSupport</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="02c89-110">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="02c89-110">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="02c89-111">**[GetSupportMask](ifoldersupport-getsupportmask.md)**</span><span class="sxs-lookup"><span data-stu-id="02c89-111">**[GetSupportMask](ifoldersupport-getsupportmask.md)**</span></span> <br/> |<span data-ttu-id="02c89-112">获取共享文件夹的支持的信息。</span><span class="sxs-lookup"><span data-stu-id="02c89-112">Gets information about a folder's support for sharing.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="02c89-113">注解</span><span class="sxs-lookup"><span data-stu-id="02c89-113">Remarks</span></span>

<span data-ttu-id="02c89-114">一般情况下，Microsoft Office Outlook 需要 MAPI 存储提供程序实现此接口，如果提供程序希望共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="02c89-114">Generally, Microsoft Office Outlook requires a MAPI store provider to implement this interface if the provider wants to share a folder.</span></span> <span data-ttu-id="02c89-115">例外情况是可以实现此接口不共享文件夹的 Exchange Server 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="02c89-115">The exception is the Exchange Server store provider, which can share folders without implementing this interface.</span></span>
  
<span data-ttu-id="02c89-116">客户端可以查询**IFolderSupport** **[IMAPIFolder](imapifolderimapicontainer.md)** 。</span><span class="sxs-lookup"><span data-stu-id="02c89-116">A client can query an **[IMAPIFolder](imapifolderimapicontainer.md)** for **IFolderSupport**.</span></span> <span data-ttu-id="02c89-117">如果成功，调用**IFolderSupport::GetSupportMask**并检查要设置的**FS_SUPPORTS_SHARING**位。</span><span class="sxs-lookup"><span data-stu-id="02c89-117">If that succeeds, call **IFolderSupport::GetSupportMask** and check for the **FS_SUPPORTS_SHARING** bit to be set.</span></span> 
  

