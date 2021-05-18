---
title: IPSTOVERRIDE1 IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDE1
api_type:
- COM
ms.assetid: d26cee81-45ea-4fd3-8a54-5f35264b5d6a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5208e77f3605b5ba861f68786d8fe5e91b990d32
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315496"
---
# <a name="ipstoverride1--iunknown"></a><span data-ttu-id="52d80-103">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="52d80-103">IPSTOVERRIDE1 : IUnknown</span></span>

  
  
<span data-ttu-id="52d80-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="52d80-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="52d80-105">允许 PST 存储 (个人) 文件覆盖 PSTDisableGrow 策略。</span><span class="sxs-lookup"><span data-stu-id="52d80-105">Allows a Personal Folders file (PST) store provider to override the PSTDisableGrow policy.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="52d80-106">继承自：</span><span class="sxs-lookup"><span data-stu-id="52d80-106">Inherits from:</span></span>  <br/> |<span data-ttu-id="52d80-107">IUnknown</span><span class="sxs-lookup"><span data-stu-id="52d80-107">IUnknown</span></span>  <br/> |
|<span data-ttu-id="52d80-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="52d80-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="52d80-109">PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="52d80-109">PST store provider</span></span>  <br/> |
|<span data-ttu-id="52d80-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="52d80-110">Called by:</span></span>  <br/> |<span data-ttu-id="52d80-111">客户端</span><span class="sxs-lookup"><span data-stu-id="52d80-111">Client</span></span>  <br/> |
|<span data-ttu-id="52d80-112">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="52d80-112">Interface identifier:</span></span>  <br/> |<span data-ttu-id="52d80-113">IID_IPSTOVERRIDE1</span><span class="sxs-lookup"><span data-stu-id="52d80-113">IID_IPSTOVERRIDE1</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="52d80-114">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="52d80-114">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="52d80-115">IPSTOVERRIDE1::GetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="52d80-115">IPSTOVERRIDE1::GetPersistedRegistrations</span></span>](ipstoverride1-getpersistedregistrations.md) <br/> |<span data-ttu-id="52d80-116">检索个人文件夹的注册列表 (.pst) 文件。</span><span class="sxs-lookup"><span data-stu-id="52d80-116">Retrieves the list of registrations for the Personal Folders (.pst) file.</span></span>  <br/> |
|[<span data-ttu-id="52d80-117">IPSTOVERRIDE1::SetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="52d80-117">IPSTOVERRIDE1::SetPersistedRegistrations</span></span>](ipstoverride1-setpersistedregistrations.md) <br/> |<span data-ttu-id="52d80-118">注册个人文件夹文件以自动解锁，以避免进一步调用 HrTrustedPSTOverrideHandlerCallback。</span><span class="sxs-lookup"><span data-stu-id="52d80-118">Registers Personal Folders files for automatic unlocking, avoiding further calls to HrTrustedPSTOverrideHandlerCallback.</span></span>  <br/> |
|[<span data-ttu-id="52d80-119">IPSTOVERRIDE1::OverridePSTDisableGrow</span><span class="sxs-lookup"><span data-stu-id="52d80-119">IPSTOVERRIDE1::OverridePSTDisableGrow</span></span>](ipstoverride1-overridepstdisablegrow.md) <br/> |<span data-ttu-id="52d80-120">解锁个人文件夹文件以增长。</span><span class="sxs-lookup"><span data-stu-id="52d80-120">Unlocks a Personal Folders file for growth.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="52d80-121">备注</span><span class="sxs-lookup"><span data-stu-id="52d80-121">Remarks</span></span>

<span data-ttu-id="52d80-122">PST 覆盖处理程序接口标识符可能未在当前具有的可下载头文件中定义，在这种情况下，您将在 [MAPI 常量](mapi-constants.md) 主题中查找它们，并可以复制它们并将其添加到代码中。</span><span class="sxs-lookup"><span data-stu-id="52d80-122">The PST Override Handler Interface Identifiers might not be defined in the downloadable header file you currently have, in which case you will find them in the [MAPI Constants](mapi-constants.md) topic, and can copy and add them to your code.</span></span> <span data-ttu-id="52d80-123">使用 Microsoft Windows 软件开发工具包 (SDK) 头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 符号名称与它们的值关联。</span><span class="sxs-lookup"><span data-stu-id="52d80-123">Use the DEFINE_GUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate globally unique identifier (GUID) symbolic names with their values.</span></span> 
  
<span data-ttu-id="52d80-124">有关详细信息，请参阅 [如何在 Outlook 2007](https://support.microsoft.com/kb/956070)中实现 PST 覆盖处理程序以绕过 PSTDisableGrow 策略。</span><span class="sxs-lookup"><span data-stu-id="52d80-124">For more information see [How to implement a PST override handler to bypass the PSTDisableGrow policy in Outlook 2007](https://support.microsoft.com/kb/956070).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52d80-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d80-125">See also</span></span>



[<span data-ttu-id="52d80-126">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="52d80-126">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

