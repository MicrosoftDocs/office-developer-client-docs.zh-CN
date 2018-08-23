---
title: MSGCALLRELEASE
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MSGCALLRELEASE
api_type:
- COM
ms.assetid: 23c08597-41f0-4f48-a63e-79962fa812bc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e9a1c416cbf992c9cbcfb5de42d302ff16e7f521
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573185"
---
# <a name="msgcallrelease"></a><span data-ttu-id="0db99-103">MSGCALLRELEASE</span><span class="sxs-lookup"><span data-stu-id="0db99-103">MSGCALLRELEASE</span></span>

  
  
<span data-ttu-id="0db99-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0db99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0db99-105">定义一个在它构建与[OpenIMsgOnIStg](openimsgonistg.md)函数**IMessage**对象的最终发行后可以释放**IStorage**接口的回调函数。</span><span class="sxs-lookup"><span data-stu-id="0db99-105">Defines a callback function that can free an **IStorage** interface after the final release of an **IMessage** object built on top of it with the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0db99-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="0db99-106">Header file:</span></span>  <br/> |<span data-ttu-id="0db99-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="0db99-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="0db99-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="0db99-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="0db99-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="0db99-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="0db99-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="0db99-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="0db99-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="0db99-111">MAPI</span></span>  <br/> |
   
```cpp
typedef void (STDAPICALLTYPE MSGCALLRELEASE)(
  ULONG  ulCallerData,
  LPMESSAGE  lpMessage );
```

## <a name="parameters"></a><span data-ttu-id="0db99-112">参数</span><span class="sxs-lookup"><span data-stu-id="0db99-112">Parameters</span></span>

 <span data-ttu-id="0db99-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="0db99-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="0db99-114">[in]包含有关**IMessage**接口调用应用程序信息。</span><span class="sxs-lookup"><span data-stu-id="0db99-114">[in] Contains calling application information about the **IMessage** interface.</span></span> 
    
 <span data-ttu-id="0db99-115">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="0db99-115">_lpMessage_</span></span>
  
> <span data-ttu-id="0db99-116">[in]顶级邮件和附件的已发布的指针。</span><span class="sxs-lookup"><span data-stu-id="0db99-116">[in] Pointer to the top-level message and attachments that have been released.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="0db99-117">返回值</span><span class="sxs-lookup"><span data-stu-id="0db99-117">Return value</span></span>

<span data-ttu-id="0db99-118">无。</span><span class="sxs-lookup"><span data-stu-id="0db99-118">None.</span></span>
  

