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
ms.openlocfilehash: d4dc72309ff090317b2353cab0b4fc2c5be41181
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430313"
---
# <a name="attmessagestatus"></a><span data-ttu-id="6a6e6-103">attMessageStatus</span><span class="sxs-lookup"><span data-stu-id="6a6e6-103">attMessageStatus</span></span>

  
  
<span data-ttu-id="6a6e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6a6e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6a6e6-105">MAPI 消息标志映射到 TNEF 标志以保持向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="6a6e6-105">MAPI message flags are mapped to TNEF flags to preserve backward compatibility.</span></span> <span data-ttu-id="6a6e6-106">所有标志都组合在一起，并采用单个字节进行编码。</span><span class="sxs-lookup"><span data-stu-id="6a6e6-106">All the flags are grouped together and encoded in a single byte.</span></span> <span data-ttu-id="6a6e6-107">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="6a6e6-107">The mappings are as follows:</span></span>
  
|<span data-ttu-id="6a6e6-108">**MAPI 邮件标志**</span><span class="sxs-lookup"><span data-stu-id="6a6e6-108">**MAPI message flags**</span></span>|<span data-ttu-id="6a6e6-109">**TNEF 标志**</span><span class="sxs-lookup"><span data-stu-id="6a6e6-109">**TNEF flags**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6a6e6-110">MSGFLAG_READ</span><span class="sxs-lookup"><span data-stu-id="6a6e6-110">MSGFLAG_READ</span></span>  <br/> |<span data-ttu-id="6a6e6-111">fmsRead</span><span class="sxs-lookup"><span data-stu-id="6a6e6-111">fmsRead</span></span>  <br/> |
|<span data-ttu-id="6a6e6-112">MSGFLAG_UNMODIFED</span><span class="sxs-lookup"><span data-stu-id="6a6e6-112">MSGFLAG_UNMODIFED</span></span>  <br/> |<span data-ttu-id="6a6e6-113">~fmsModified</span><span class="sxs-lookup"><span data-stu-id="6a6e6-113">~fmsModified</span></span>  <br/> |
|<span data-ttu-id="6a6e6-114">MSGFLAG_SUBMIT</span><span class="sxs-lookup"><span data-stu-id="6a6e6-114">MSGFLAG_SUBMIT</span></span>  <br/> |<span data-ttu-id="6a6e6-115">fmsSubmitted</span><span class="sxs-lookup"><span data-stu-id="6a6e6-115">fmsSubmitted</span></span>  <br/> |
|<span data-ttu-id="6a6e6-116">MSGFLAG_HASATTACH</span><span class="sxs-lookup"><span data-stu-id="6a6e6-116">MSGFLAG_HASATTACH</span></span>  <br/> |<span data-ttu-id="6a6e6-117">fmsHasAttach</span><span class="sxs-lookup"><span data-stu-id="6a6e6-117">fmsHasAttach</span></span>  <br/> |
|<span data-ttu-id="6a6e6-118">MSGFLAG_UNSENT</span><span class="sxs-lookup"><span data-stu-id="6a6e6-118">MSGFLAG_UNSENT</span></span>  <br/> |<span data-ttu-id="6a6e6-119">fmsLocal</span><span class="sxs-lookup"><span data-stu-id="6a6e6-119">fmsLocal</span></span>  <br/> |
   
<span data-ttu-id="6a6e6-120">这些标志在 TNEF 中定义。H 头文件。</span><span class="sxs-lookup"><span data-stu-id="6a6e6-120">These flags are defined in the TNEF.H header file.</span></span>
  

