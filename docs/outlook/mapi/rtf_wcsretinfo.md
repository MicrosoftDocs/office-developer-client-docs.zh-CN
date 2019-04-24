---
title: RTF_WCSRETINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 62561d8d-33cb-e482-7fa0-132afe2b464a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: cfa18c215fc98610b836db31e2a07581291910be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315783"
---
# <a name="rtfwcsretinfo"></a><span data-ttu-id="7651b-103">RTF_WCSRETINFO</span><span class="sxs-lookup"><span data-stu-id="7651b-103">RTF_WCSRETINFO</span></span>

<span data-ttu-id="7651b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7651b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7651b-105">此结构提供了从解压缩以压缩的 rtf 格式 (RTF) 封装的邮件正文返回的本机格式的信息。</span><span class="sxs-lookup"><span data-stu-id="7651b-105">This structure provides information about a stream in native format returned from decompressing the body of a message that is encapsulated in compressed Rich Text Format (RTF).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="7651b-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="7651b-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a><span data-ttu-id="7651b-107">成员</span><span class="sxs-lookup"><span data-stu-id="7651b-107">Members</span></span>

<span data-ttu-id="7651b-108">_size_</span><span class="sxs-lookup"><span data-stu-id="7651b-108">_size_</span></span>
  
> <span data-ttu-id="7651b-109">以字节数表示的**RTF_WCSRETINFO**结构的大小。</span><span class="sxs-lookup"><span data-stu-id="7651b-109">The size of the **RTF_WCSRETINFO** structure in number of bytes.</span></span> 
    
<span data-ttu-id="7651b-110">_ulStreamFlags_</span><span class="sxs-lookup"><span data-stu-id="7651b-110">_ulStreamFlags_</span></span>
  
> <span data-ttu-id="7651b-111">这是一个指示本机正文的格式的值。</span><span class="sxs-lookup"><span data-stu-id="7651b-111">This is a value that indicates the format of the native body.</span></span> <span data-ttu-id="7651b-112">仅当**MAPI_NATIVE_BODY**标志在传递给[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的[RTF_WCSINFO](rtf_wcsinfo.md)结构的_ulFlags_参数中传递时, 此值才有效。</span><span class="sxs-lookup"><span data-stu-id="7651b-112">This value is only valid if the **MAPI_NATIVE_BODY** flag is passed in the  _ulFlags_ parameter of the [RTF_WCSINFO](rtf_wcsinfo.md) structure that is passed to the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span> <span data-ttu-id="7651b-113">此值可以是下列值之一:</span><span class="sxs-lookup"><span data-stu-id="7651b-113">This can be one of the following values:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7651b-114">MAPI_NATIVE_BODY_TYPE_RTF</span><span class="sxs-lookup"><span data-stu-id="7651b-114">MAPI_NATIVE_BODY_TYPE_RTF</span></span>  <br/> |<span data-ttu-id="7651b-115">仅当_ulFlags_包含**MAPI_NATIVE_BODY**标志, 且正文为 RTF 时才使用此值。</span><span class="sxs-lookup"><span data-stu-id="7651b-115">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is RTF.</span></span>  <br/> |
|<span data-ttu-id="7651b-116">MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT</span><span class="sxs-lookup"><span data-stu-id="7651b-116">MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT</span></span>  <br/> |<span data-ttu-id="7651b-117">仅当_ulFlags_包含**MAPI_NATIVE_BODY**标志, 且正文为纯文本格式时才使用此值。</span><span class="sxs-lookup"><span data-stu-id="7651b-117">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is plain text format.</span></span>  <br/> |
|<span data-ttu-id="7651b-118">MAPI_NATIVE_BODY_TYPE_HTML</span><span class="sxs-lookup"><span data-stu-id="7651b-118">MAPI_NATIVE_BODY_TYPE_HTML</span></span>  <br/> |<span data-ttu-id="7651b-119">仅当_ulFlags_包含**MAPI_NATIVE_BODY**标志, 并且正文是超文本标记语言 (HTML) 格式时, 才使用此值。</span><span class="sxs-lookup"><span data-stu-id="7651b-119">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is Hypertext Markup Language (HTML) format.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="7651b-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7651b-120">See also</span></span>

- [<span data-ttu-id="7651b-121">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="7651b-121">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)

