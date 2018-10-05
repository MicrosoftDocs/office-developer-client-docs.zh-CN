---
title: IPSTOVERRIDEREQ IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDEREQ
api_type:
- COM
ms.assetid: 22f497de-4afe-4433-965d-c3b5a66b05da
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7f3f6ae2b9849710bf44d3635fc7bb9a62016f48
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389104"
---
# <a name="ipstoverridereq--iunknown"></a><span data-ttu-id="1c281-103">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1c281-103">IPSTOVERRIDEREQ : IUnknown</span></span>

  
  
<span data-ttu-id="1c281-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c281-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c281-105">访问资源的个人文件夹文件 (PST) 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="1c281-105">Accesses resources of a Personal Folders file (PST) store provider.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1c281-106">继承：</span><span class="sxs-lookup"><span data-stu-id="1c281-106">Inherits from:</span></span>  <br/> |<span data-ttu-id="1c281-107">IUnknown</span><span class="sxs-lookup"><span data-stu-id="1c281-107">IUnknown</span></span>  <br/> |
|<span data-ttu-id="1c281-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="1c281-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="1c281-109">PST 存储提供程序</span><span class="sxs-lookup"><span data-stu-id="1c281-109">PST store provider</span></span>  <br/> |
|<span data-ttu-id="1c281-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="1c281-110">Called by:</span></span>  <br/> |<span data-ttu-id="1c281-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="1c281-111">Client applications</span></span>  <br/> |
|<span data-ttu-id="1c281-112">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="1c281-112">Interface identifier:</span></span>  <br/> |<span data-ttu-id="1c281-113">IID_IPSTOVERRIDEREQ</span><span class="sxs-lookup"><span data-stu-id="1c281-113">IID_IPSTOVERRIDEREQ</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="1c281-114">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="1c281-114">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="1c281-115">IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler</span><span class="sxs-lookup"><span data-stu-id="1c281-115">IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler</span></span>](ipstoverridereq-registertrustedpstoverridehandler.md) <br/> |<span data-ttu-id="1c281-116">启动个人文件夹 (.pst) 文件的解除过程。</span><span class="sxs-lookup"><span data-stu-id="1c281-116">Initiates the unlocking procedure for a Personal Folders (.pst) file.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1c281-117">说明</span><span class="sxs-lookup"><span data-stu-id="1c281-117">Remarks</span></span>

<span data-ttu-id="1c281-118">未可能可下载头文件后，这种情况下将在[MAPI 常量](mapi-constants.md)主题中，找到这些和可以复制，并将其添加到您的代码中定义 PST 重写处理程序界面标识符。</span><span class="sxs-lookup"><span data-stu-id="1c281-118">The PST Override Handler Interface Identifiers might not be defined in the downloadable header file you currently have, in which case you will find them in the [MAPI Constants](mapi-constants.md) topic, and can copy and add them to your code.</span></span> <span data-ttu-id="1c281-119">使用 Microsoft Windows 软件开发工具包 (SDK) 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏将全局唯一标识符 (GUID) 的符号名称相关联的值。</span><span class="sxs-lookup"><span data-stu-id="1c281-119">Use the DEFINE_GUID macro defined in the Microsoft Windows Software Development Kit (SDK) header file guiddef.h to associate globally unique identifier (GUID) symbolic names with their values.</span></span> 
  
<span data-ttu-id="1c281-120">有关详细信息，请参阅[如何实现 PST 重写处理程序，以绕过 Outlook 2007 中的 PSTDisableGrow 策略](https://support.microsoft.com/kb/956070)。</span><span class="sxs-lookup"><span data-stu-id="1c281-120">For more information see [How to implement a PST override handler to bypass the PSTDisableGrow policy in Outlook 2007](https://support.microsoft.com/kb/956070).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1c281-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c281-121">See also</span></span>



[<span data-ttu-id="1c281-122">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1c281-122">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md)

