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
ms.openlocfilehash: 9ffaab1e9cc381be2abfb389f4b72067dca2438b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405910"
---
# <a name="msgcallrelease"></a><span data-ttu-id="aa229-103">MSGCALLRELEASE</span><span class="sxs-lookup"><span data-stu-id="aa229-103">MSGCALLRELEASE</span></span>

  
  
<span data-ttu-id="aa229-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aa229-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aa229-105">定义一个回调函数，该函数可在 **IMessage** 对象最终发布后使用 [OpenIMsgOnIStg](openimsgonistg.md)函数释放 **IStorage** 接口。</span><span class="sxs-lookup"><span data-stu-id="aa229-105">Defines a callback function that can free an **IStorage** interface after the final release of an **IMessage** object built on top of it with the [OpenIMsgOnIStg](openimsgonistg.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="aa229-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="aa229-106">Header file:</span></span>  <br/> |<span data-ttu-id="aa229-107">Imessage.h</span><span class="sxs-lookup"><span data-stu-id="aa229-107">Imessage.h</span></span>  <br/> |
|<span data-ttu-id="aa229-108">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="aa229-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="aa229-109">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="aa229-109">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="aa229-110">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="aa229-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="aa229-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="aa229-111">MAPI</span></span>  <br/> |
   
```cpp
typedef void (STDAPICALLTYPE MSGCALLRELEASE)(
  ULONG  ulCallerData,
  LPMESSAGE  lpMessage );
```

## <a name="parameters"></a><span data-ttu-id="aa229-112">参数</span><span class="sxs-lookup"><span data-stu-id="aa229-112">Parameters</span></span>

 <span data-ttu-id="aa229-113">_ulCallerData_</span><span class="sxs-lookup"><span data-stu-id="aa229-113">_ulCallerData_</span></span>
  
> <span data-ttu-id="aa229-114">[in]包含有关 **IMessage 接口的调用应用程序** 信息。</span><span class="sxs-lookup"><span data-stu-id="aa229-114">[in] Contains calling application information about the **IMessage** interface.</span></span> 
    
 <span data-ttu-id="aa229-115">_lpMessage_</span><span class="sxs-lookup"><span data-stu-id="aa229-115">_lpMessage_</span></span>
  
> <span data-ttu-id="aa229-116">[in]指向已释放的顶级邮件和附件的指针。</span><span class="sxs-lookup"><span data-stu-id="aa229-116">[in] Pointer to the top-level message and attachments that have been released.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="aa229-117">返回值</span><span class="sxs-lookup"><span data-stu-id="aa229-117">Return value</span></span>

<span data-ttu-id="aa229-118">无。</span><span class="sxs-lookup"><span data-stu-id="aa229-118">None.</span></span>
  

