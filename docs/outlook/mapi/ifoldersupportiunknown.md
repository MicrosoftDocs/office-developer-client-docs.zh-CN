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
ms.openlocfilehash: da186e6804fc3d3c820551fee66519a2ff76f0db
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351385"
---
# <a name="ifoldersupport--iunknown"></a><span data-ttu-id="5dc9a-103">IFolderSupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5dc9a-103">IFolderSupport : IUnknown</span></span>

  
  
<span data-ttu-id="5dc9a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5dc9a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5dc9a-105">提供有关文件夹支持共享的信息。</span><span class="sxs-lookup"><span data-stu-id="5dc9a-105">Provides information about a folder's support for sharing.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5dc9a-106">提供者：</span><span class="sxs-lookup"><span data-stu-id="5dc9a-106">Provided by:</span></span>  <br/> |<span data-ttu-id="5dc9a-107">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="5dc9a-107">Message store provider</span></span>  <br/> |
|<span data-ttu-id="5dc9a-108">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="5dc9a-108">Interface identifier:</span></span>  <br/> |<span data-ttu-id="5dc9a-109">IID_IFolderSupport</span><span class="sxs-lookup"><span data-stu-id="5dc9a-109">IID_IFolderSupport</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="5dc9a-110">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="5dc9a-110">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="5dc9a-111">**[GetSupportMask](ifoldersupport-getsupportmask.md)**</span><span class="sxs-lookup"><span data-stu-id="5dc9a-111">**[GetSupportMask](ifoldersupport-getsupportmask.md)**</span></span> <br/> |<span data-ttu-id="5dc9a-112">获取有关文件夹支持共享的信息。</span><span class="sxs-lookup"><span data-stu-id="5dc9a-112">Gets information about a folder's support for sharing.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5dc9a-113">注解</span><span class="sxs-lookup"><span data-stu-id="5dc9a-113">Remarks</span></span>

<span data-ttu-id="5dc9a-114">通常, 如果提供程序想要共享文件夹, Microsoft Office Outlook 需要 MAPI 存储提供程序来实现此接口。</span><span class="sxs-lookup"><span data-stu-id="5dc9a-114">Generally, Microsoft Office Outlook requires a MAPI store provider to implement this interface if the provider wants to share a folder.</span></span> <span data-ttu-id="5dc9a-115">例外情况是 Exchange 服务器存储提供程序, 它可以在不实现此接口的情况下共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="5dc9a-115">The exception is the Exchange Server store provider, which can share folders without implementing this interface.</span></span>
  
<span data-ttu-id="5dc9a-116">客户端可以查询**IFolderSupport**的**[IMAPIFolder](imapifolderimapicontainer.md)** 。</span><span class="sxs-lookup"><span data-stu-id="5dc9a-116">A client can query an **[IMAPIFolder](imapifolderimapicontainer.md)** for **IFolderSupport**.</span></span> <span data-ttu-id="5dc9a-117">如果成功, 请调用**IFolderSupport:: GetSupportMask**并检查要设置的**FS_SUPPORTS_SHARING**位。</span><span class="sxs-lookup"><span data-stu-id="5dc9a-117">If that succeeds, call **IFolderSupport::GetSupportMask** and check for the **FS_SUPPORTS_SHARING** bit to be set.</span></span> 
  

