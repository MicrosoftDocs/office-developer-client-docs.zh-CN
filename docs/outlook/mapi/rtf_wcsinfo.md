---
title: RTF_WCSINFO
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0c94501e-0ec7-e836-33a7-adcf5a61b375
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2dd9f002401f8de52a9ad187b7e5850d47caf8a7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587381"
---
# <a name="rtfwcsinfo"></a><span data-ttu-id="f3891-103">RTF_WCSINFO</span><span class="sxs-lookup"><span data-stu-id="f3891-103">RTF_WCSINFO</span></span>

  
  
<span data-ttu-id="f3891-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3891-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3891-105">此结构使您可以指定要解压缩压缩富文本格式 (RTF) 中的邮件正文以及 （可选） 以其本机格式返回正文的流信息。</span><span class="sxs-lookup"><span data-stu-id="f3891-105">This structure enables you to specify information to decompress the body of a message in compressed Rich Text Format (RTF) and, optionally, return the body stream in its native format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="f3891-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="f3891-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG size; 
    ULONG ulFlags; 
    ULONG ulInCodePage; 
    ULONG ulOutCodePage; 
} RTF_WCSINFO;

```

## <a name="members"></a><span data-ttu-id="f3891-107">Members</span><span class="sxs-lookup"><span data-stu-id="f3891-107">Members</span></span>

 <span data-ttu-id="f3891-108">_size_</span><span class="sxs-lookup"><span data-stu-id="f3891-108">_size_</span></span>
  
> <span data-ttu-id="f3891-109">**RTF_WCSINFO**结构以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="f3891-109">The size of the **RTF_WCSINFO** structure in number of bytes.</span></span> 
    
 <span data-ttu-id="f3891-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f3891-110">_ulFlags_</span></span>
  
> <span data-ttu-id="f3891-111">这是[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数选项标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f3891-111">This is the bitmask of option flags for the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span> <span data-ttu-id="f3891-112">受支持的选项标志是：</span><span class="sxs-lookup"><span data-stu-id="f3891-112">The supported option flags are:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="f3891-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="f3891-113">MAPI_MODIFY</span></span>  <br/> |<span data-ttu-id="f3891-114">这指示客户端是否打算编写返回打包的流界面。</span><span class="sxs-lookup"><span data-stu-id="f3891-114">This indicates whether the client intends to write the wrapped stream interface that is returned.</span></span>  <br/> |
|<span data-ttu-id="f3891-115">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="f3891-115">STORE_UNCOMPRESSED_RTF</span></span>  <br/> |<span data-ttu-id="f3891-116">这指示是否应记下解压缩后的 RTF 写入[WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的_lpCompressedRTFStream_指针所指向的流。</span><span class="sxs-lookup"><span data-stu-id="f3891-116">This indicates whether the decompressed RTF is supposed to be written to the stream that is pointed to by the  _lpCompressedRTFStream_ pointer of the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span>  <br/> |
|<span data-ttu-id="f3891-117">MAPI_NATIVE_BODY</span><span class="sxs-lookup"><span data-stu-id="f3891-117">MAPI_NATIVE_BODY</span></span>  <br/> |<span data-ttu-id="f3891-118">这指示是否记下解压缩后的流也返回流之前转换为本机正文。</span><span class="sxs-lookup"><span data-stu-id="f3891-118">This indicates whether the decompressed stream is also converted to the native body before returning the stream.</span></span> <span data-ttu-id="f3891-119">不能与**MAPI_MODIFY**标志组合此标志。</span><span class="sxs-lookup"><span data-stu-id="f3891-119">This flag cannot be combined with the **MAPI_MODIFY** flag.</span></span>  <br/> |
   
 <span data-ttu-id="f3891-120">_ulInCodePage_</span><span class="sxs-lookup"><span data-stu-id="f3891-120">_ulInCodePage_</span></span>
  
> <span data-ttu-id="f3891-121">这是邮件的代码页值。</span><span class="sxs-lookup"><span data-stu-id="f3891-121">This is the code page value of the message.</span></span> <span data-ttu-id="f3891-122">通常情况下，从邮件上的[PidTagInternetCodepage 规范属性](pidtaginternetcodepage-canonical-property.md)获取此值。</span><span class="sxs-lookup"><span data-stu-id="f3891-122">Typically, this value is obtained from the [PidTagInternetCodepage Canonical Property](pidtaginternetcodepage-canonical-property.md) on the message.</span></span> <span data-ttu-id="f3891-123">_UlFlags_中传递**MAPI_NATIVE_BODY**标志时才使用此值。</span><span class="sxs-lookup"><span data-stu-id="f3891-123">This value is only used when the **MAPI_NATIVE_BODY** flag is passed in  _ulFlags_.</span></span> <span data-ttu-id="f3891-124">否则，此值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="f3891-124">Otherwise, this value is ignored.</span></span>
    
 <span data-ttu-id="f3891-125">_ulOutCodePage_</span><span class="sxs-lookup"><span data-stu-id="f3891-125">_ulOutCodePage_</span></span>
  
> <span data-ttu-id="f3891-126">这是数据流的返回记下解压缩后所需的代码页值。</span><span class="sxs-lookup"><span data-stu-id="f3891-126">This is the code page value of the returned decompressed stream that you want.</span></span> <span data-ttu-id="f3891-127">如果设置为非零值， [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数会将流转换为指定的代码页。</span><span class="sxs-lookup"><span data-stu-id="f3891-127">If this is set to a non-zero value, the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function converts the stream to the specified code page.</span></span> <span data-ttu-id="f3891-128">如果设置为零值，MAPI 决定要使用的代码页。</span><span class="sxs-lookup"><span data-stu-id="f3891-128">If this is set to a zero value, MAPI decides which code page to use.</span></span> <span data-ttu-id="f3891-129">仅当**MAPI_NATIVE_BODY**标志传入中_ulFlags_，并且的正文格式不为 RTF 时，则使用此值。</span><span class="sxs-lookup"><span data-stu-id="f3891-129">This value is used only when the **MAPI_NATIVE_BODY** flag is passed in  _ulFlags_, and the body format is not RTF.</span></span> <span data-ttu-id="f3891-130">否则，此值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="f3891-130">Otherwise, this value is ignored.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f3891-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3891-131">See also</span></span>



[<span data-ttu-id="f3891-132">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="f3891-132">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)

