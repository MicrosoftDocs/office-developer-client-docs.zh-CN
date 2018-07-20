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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: db2853080b1fc2ff3a346dcfb8d112237b7f3459
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776059"
---
# <a name="ipstoverride1--iunknown"></a><span data-ttu-id="fe5ca-103">IPSTOVERRIDE1: IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe5ca-103">IPSTOVERRIDE1 : IUnknown</span></span>

  
  
<span data-ttu-id="fe5ca-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="fe5ca-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fe5ca-105">允许个人文件夹文件 (PST) 存储提供程序重写 PSTDisableGrow 策略。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-105">Allows a Personal Folders file (PST) store provider to override the PSTDisableGrow policy.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fe5ca-106">继承：</span><span class="sxs-lookup"><span data-stu-id="fe5ca-106">Inherits from:</span></span>  <br/> |<span data-ttu-id="fe5ca-107">IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe5ca-107">IUnknown</span></span>  <br/> |
|<span data-ttu-id="fe5ca-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="fe5ca-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fe5ca-109">PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="fe5ca-109">PST store provider</span></span>  <br/> |
|<span data-ttu-id="fe5ca-110">调用：</span><span class="sxs-lookup"><span data-stu-id="fe5ca-110">Called by:</span></span>  <br/> |<span data-ttu-id="fe5ca-111">客户端</span><span class="sxs-lookup"><span data-stu-id="fe5ca-111">Client</span></span>  <br/> |
|<span data-ttu-id="fe5ca-112">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="fe5ca-112">Interface identifier:</span></span>  <br/> |<span data-ttu-id="fe5ca-113">IID_IPSTOVERRIDE1</span><span class="sxs-lookup"><span data-stu-id="fe5ca-113">IID_IPSTOVERRIDE1</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="fe5ca-114">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="fe5ca-114">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="fe5ca-115">IPSTOVERRIDE1::GetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="fe5ca-115">IPSTOVERRIDE1::GetPersistedRegistrations</span></span>](ipstoverride1-getpersistedregistrations.md) <br/> |<span data-ttu-id="fe5ca-116">检索的登记个人文件夹 (.pst) 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-116">Retrieves the list of registrations for the Personal Folders (.pst) file.</span></span>  <br/> |
|[<span data-ttu-id="fe5ca-117">IPSTOVERRIDE1::SetPersistedRegistrations</span><span class="sxs-lookup"><span data-stu-id="fe5ca-117">IPSTOVERRIDE1::SetPersistedRegistrations</span></span>](ipstoverride1-setpersistedregistrations.md) <br/> |<span data-ttu-id="fe5ca-118">避免进一步调用 HrTrustedPSTOverrideHandlerCallback 注册自动解锁个人文件夹文件。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-118">Registers Personal Folders files for automatic unlocking, avoiding further calls to HrTrustedPSTOverrideHandlerCallback.</span></span>  <br/> |
|[<span data-ttu-id="fe5ca-119">IPSTOVERRIDE1::OverridePSTDisableGrow</span><span class="sxs-lookup"><span data-stu-id="fe5ca-119">IPSTOVERRIDE1::OverridePSTDisableGrow</span></span>](ipstoverride1-overridepstdisablegrow.md) <br/> |<span data-ttu-id="fe5ca-120">解除对个人文件夹文件增长。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-120">Unlocks a Personal Folders file for growth.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fe5ca-121">备注</span><span class="sxs-lookup"><span data-stu-id="fe5ca-121">Remarks</span></span>

<span data-ttu-id="fe5ca-122">未可能可下载头文件后，这种情况下将在[MAPI 常量](mapi-constants.md)主题中，找到这些和可以复制，并将其添加到您的代码中定义 PST 重写处理程序界面标识符。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-122">The PST Override Handler Interface Identifiers might not be defined in the downloadable header file you currently have, in which case you will find them in the [MAPI Constants](mapi-constants.md) topic, and can copy and add them to your code.</span></span> <span data-ttu-id="fe5ca-123">使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 的符号名称相关联的值。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-123">Use the DEFINE_GUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate globally unique identifier (GUID) symbolic names with their values.</span></span> 
  
<span data-ttu-id="fe5ca-124">有关详细信息，请参阅[如何实现 PST 重写处理程序，以绕过 Outlook 2007 中的 PSTDisableGrow 策略](http://support.microsoft.com/kb/956070)。</span><span class="sxs-lookup"><span data-stu-id="fe5ca-124">For more information see [How to implement a PST override handler to bypass the PSTDisableGrow policy in Outlook 2007](http://support.microsoft.com/kb/956070).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fe5ca-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe5ca-125">See also</span></span>



[<span data-ttu-id="fe5ca-126">IPSTOVERRIDEREQ: IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe5ca-126">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)
