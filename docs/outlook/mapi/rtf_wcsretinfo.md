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
ms.openlocfilehash: bf8cf115c6188b5058717437c470e11797ff5b9a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564960"
---
# <a name="rtfwcsretinfo"></a><span data-ttu-id="36fcb-103">RTF_WCSRETINFO</span><span class="sxs-lookup"><span data-stu-id="36fcb-103">RTF_WCSRETINFO</span></span>

<span data-ttu-id="36fcb-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="36fcb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="36fcb-105">此结构提供有关本机格式返回从解压缩封装压缩富文本格式 (RTF) 中的邮件正文中的流信息。</span><span class="sxs-lookup"><span data-stu-id="36fcb-105">This structure provides information about a stream in native format returned from decompressing the body of a message that is encapsulated in compressed Rich Text Format (RTF).</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="36fcb-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="36fcb-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG size;    
    ULONG ulStreamFlags; 
} RTF_WCSRETINFO;
```

## <a name="members"></a><span data-ttu-id="36fcb-107">Members</span><span class="sxs-lookup"><span data-stu-id="36fcb-107">Members</span></span>

<span data-ttu-id="36fcb-108">_size_</span><span class="sxs-lookup"><span data-stu-id="36fcb-108">_size_</span></span>
  
> <span data-ttu-id="36fcb-109">**RTF_WCSRETINFO**结构以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="36fcb-109">The size of the **RTF_WCSRETINFO** structure in number of bytes.</span></span> 
    
<span data-ttu-id="36fcb-110">_ulStreamFlags_</span><span class="sxs-lookup"><span data-stu-id="36fcb-110">_ulStreamFlags_</span></span>
  
> <span data-ttu-id="36fcb-111">这是一个值，指示本机正文的格式。</span><span class="sxs-lookup"><span data-stu-id="36fcb-111">This is a value that indicates the format of the native body.</span></span> <span data-ttu-id="36fcb-112">此值才有效如果传递给[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的[RTF_WCSINFO](rtf_wcsinfo.md)结构的_ulFlags_参数中传递**MAPI_NATIVE_BODY**标志。</span><span class="sxs-lookup"><span data-stu-id="36fcb-112">This value is only valid if the **MAPI_NATIVE_BODY** flag is passed in the  _ulFlags_ parameter of the [RTF_WCSINFO](rtf_wcsinfo.md) structure that is passed to the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span> <span data-ttu-id="36fcb-113">这可以是下列值之一：</span><span class="sxs-lookup"><span data-stu-id="36fcb-113">This can be one of the following values:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="36fcb-114">MAPI_NATIVE_BODY_TYPE_RTF</span><span class="sxs-lookup"><span data-stu-id="36fcb-114">MAPI_NATIVE_BODY_TYPE_RTF</span></span>  <br/> |<span data-ttu-id="36fcb-115">如果_ulFlags_包括**MAPI_NATIVE_BODY**标志，而且正文时 RTF，则仅使用此值。</span><span class="sxs-lookup"><span data-stu-id="36fcb-115">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is RTF.</span></span>  <br/> |
|<span data-ttu-id="36fcb-116">MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT</span><span class="sxs-lookup"><span data-stu-id="36fcb-116">MAPI_NATIVE_BODY_TYPE_PLAIN_TEXT</span></span>  <br/> |<span data-ttu-id="36fcb-117">如果_ulFlags_包括**MAPI_NATIVE_BODY**标志，和正文采用纯文本格式，则仅使用此值。</span><span class="sxs-lookup"><span data-stu-id="36fcb-117">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is plain text format.</span></span>  <br/> |
|<span data-ttu-id="36fcb-118">MAPI_NATIVE_BODY_TYPE_HTML</span><span class="sxs-lookup"><span data-stu-id="36fcb-118">MAPI_NATIVE_BODY_TYPE_HTML</span></span>  <br/> |<span data-ttu-id="36fcb-119">如果_ulFlags_包括**MAPI_NATIVE_BODY**标志，而且正文时的超文本标记语言 (HTML) 格式，则仅使用此值。</span><span class="sxs-lookup"><span data-stu-id="36fcb-119">This value is only used if  _ulFlags_ includes the **MAPI_NATIVE_BODY** flag, and the body is Hypertext Markup Language (HTML) format.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="36fcb-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36fcb-120">See also</span></span>

- [<span data-ttu-id="36fcb-121">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="36fcb-121">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)

