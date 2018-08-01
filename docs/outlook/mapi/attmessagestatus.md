---
title: attMessageStatus
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 8f55470a-65b3-4210-a7d2-9031cb17ca80
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 158e4db4b0f80b80385e85c8afa16fa515dc61b1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774590"
---
# <a name="attmessagestatus"></a><span data-ttu-id="ebd5d-103">attMessageStatus</span><span class="sxs-lookup"><span data-stu-id="ebd5d-103">attMessageStatus</span></span>

  
  
<span data-ttu-id="ebd5d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ebd5d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ebd5d-105">MAPI 邮件标志映射到 TNEF 标志保留向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="ebd5d-105">MAPI message flags are mapped to TNEF flags to preserve backward compatibility.</span></span> <span data-ttu-id="ebd5d-106">所有标志的组合在一起，并单字节编码。</span><span class="sxs-lookup"><span data-stu-id="ebd5d-106">All the flags are grouped together and encoded in a single byte.</span></span> <span data-ttu-id="ebd5d-107">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="ebd5d-107">The mappings are as follows:</span></span>
  
|<span data-ttu-id="ebd5d-108">**MAPI 邮件标志**</span><span class="sxs-lookup"><span data-stu-id="ebd5d-108">**MAPI message flags**</span></span>|<span data-ttu-id="ebd5d-109">**TNEF 标志**</span><span class="sxs-lookup"><span data-stu-id="ebd5d-109">**TNEF flags**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebd5d-110">MSGFLAG_READ</span><span class="sxs-lookup"><span data-stu-id="ebd5d-110">MSGFLAG_READ</span></span>  <br/> |<span data-ttu-id="ebd5d-111">fmsRead</span><span class="sxs-lookup"><span data-stu-id="ebd5d-111">fmsRead</span></span>  <br/> |
|<span data-ttu-id="ebd5d-112">MSGFLAG_UNMODIFED</span><span class="sxs-lookup"><span data-stu-id="ebd5d-112">MSGFLAG_UNMODIFED</span></span>  <br/> |<span data-ttu-id="ebd5d-113">~ fmsModified</span><span class="sxs-lookup"><span data-stu-id="ebd5d-113">~fmsModified</span></span>  <br/> |
|<span data-ttu-id="ebd5d-114">MSGFLAG_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="ebd5d-114">MSGFLAG_SUBMIT</span></span>  <br/> |<span data-ttu-id="ebd5d-115">fmsSubmitted</span><span class="sxs-lookup"><span data-stu-id="ebd5d-115">fmsSubmitted</span></span>  <br/> |
|<span data-ttu-id="ebd5d-116">MSGFLAG_HASATTACH</span><span class="sxs-lookup"><span data-stu-id="ebd5d-116">MSGFLAG_HASATTACH</span></span>  <br/> |<span data-ttu-id="ebd5d-117">fmsHasAttach</span><span class="sxs-lookup"><span data-stu-id="ebd5d-117">fmsHasAttach</span></span>  <br/> |
|<span data-ttu-id="ebd5d-118">MSGFLAG_UNSENT</span><span class="sxs-lookup"><span data-stu-id="ebd5d-118">MSGFLAG_UNSENT</span></span>  <br/> |<span data-ttu-id="ebd5d-119">fmsLocal</span><span class="sxs-lookup"><span data-stu-id="ebd5d-119">fmsLocal</span></span>  <br/> |
   
<span data-ttu-id="ebd5d-120">这些标志 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="ebd5d-120">These flags are defined in the TNEF.H header file.</span></span>
  

