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
ms.openlocfilehash: 6bec29aa0e88e0224f9cd6049553f2df6379e23d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430530"
---
# <a name="rtf_wcsinfo"></a><span data-ttu-id="10621-103">RTF_WCSINFO</span><span class="sxs-lookup"><span data-stu-id="10621-103">RTF_WCSINFO</span></span>

  
  
<span data-ttu-id="10621-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="10621-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="10621-105">利用此结构，您可以指定信息以压缩 RTF 格式 (RTF 格式解压缩邮件正文) （可选）以本机格式返回正文流。</span><span class="sxs-lookup"><span data-stu-id="10621-105">This structure enables you to specify information to decompress the body of a message in compressed Rich Text Format (RTF) and, optionally, return the body stream in its native format.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="10621-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="10621-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG size; 
    ULONG ulFlags; 
    ULONG ulInCodePage; 
    ULONG ulOutCodePage; 
} RTF_WCSINFO;

```

## <a name="members"></a><span data-ttu-id="10621-107">成员</span><span class="sxs-lookup"><span data-stu-id="10621-107">Members</span></span>

 <span data-ttu-id="10621-108">_size_</span><span class="sxs-lookup"><span data-stu-id="10621-108">_size_</span></span>
  
> <span data-ttu-id="10621-109">结构的大小 **RTF_WCSINFO** 字节数。</span><span class="sxs-lookup"><span data-stu-id="10621-109">The size of the **RTF_WCSINFO** structure in number of bytes.</span></span> 
    
 <span data-ttu-id="10621-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="10621-110">_ulFlags_</span></span>
  
> <span data-ttu-id="10621-111">这是 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) 函数的选项标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="10621-111">This is the bitmask of option flags for the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span> <span data-ttu-id="10621-112">支持的选项标志包括：</span><span class="sxs-lookup"><span data-stu-id="10621-112">The supported option flags are:</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="10621-113">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="10621-113">MAPI_MODIFY</span></span>  <br/> |<span data-ttu-id="10621-114">这指示客户端是否打算编写返回的封装流接口。</span><span class="sxs-lookup"><span data-stu-id="10621-114">This indicates whether the client intends to write the wrapped stream interface that is returned.</span></span>  <br/> |
|<span data-ttu-id="10621-115">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="10621-115">STORE_UNCOMPRESSED_RTF</span></span>  <br/> |<span data-ttu-id="10621-116">这指示解压缩的 RTF 是否应该写入到 [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md)函数的 _lpCompressedRTFStream_ 指针指向的流。</span><span class="sxs-lookup"><span data-stu-id="10621-116">This indicates whether the decompressed RTF is supposed to be written to the stream that is pointed to by the  _lpCompressedRTFStream_ pointer of the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function.</span></span>  <br/> |
|<span data-ttu-id="10621-117">MAPI_NATIVE_BODY</span><span class="sxs-lookup"><span data-stu-id="10621-117">MAPI_NATIVE_BODY</span></span>  <br/> |<span data-ttu-id="10621-118">这指示在返回流之前解压缩的流是否也转换为本机正文。</span><span class="sxs-lookup"><span data-stu-id="10621-118">This indicates whether the decompressed stream is also converted to the native body before returning the stream.</span></span> <span data-ttu-id="10621-119">此标志不能与 MAPI_MODIFY **标志组合** 。</span><span class="sxs-lookup"><span data-stu-id="10621-119">This flag cannot be combined with the **MAPI_MODIFY** flag.</span></span>  <br/> |
   
 <span data-ttu-id="10621-120">_ulInCodePage_</span><span class="sxs-lookup"><span data-stu-id="10621-120">_ulInCodePage_</span></span>
  
> <span data-ttu-id="10621-121">这是邮件的代码页值。</span><span class="sxs-lookup"><span data-stu-id="10621-121">This is the code page value of the message.</span></span> <span data-ttu-id="10621-122">通常，此值从邮件上的 [PidTagInternetCodepage](pidtaginternetcodepage-canonical-property.md) 规范属性获取。</span><span class="sxs-lookup"><span data-stu-id="10621-122">Typically, this value is obtained from the [PidTagInternetCodepage Canonical Property](pidtaginternetcodepage-canonical-property.md) on the message.</span></span> <span data-ttu-id="10621-123">只有在 _ulFlags_**中传递** MAPI_NATIVE_BODY 标志时，才使用此值。</span><span class="sxs-lookup"><span data-stu-id="10621-123">This value is only used when the **MAPI_NATIVE_BODY** flag is passed in  _ulFlags_.</span></span> <span data-ttu-id="10621-124">否则，将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="10621-124">Otherwise, this value is ignored.</span></span>
    
 <span data-ttu-id="10621-125">_ulOutCodePage_</span><span class="sxs-lookup"><span data-stu-id="10621-125">_ulOutCodePage_</span></span>
  
> <span data-ttu-id="10621-126">这是您返回的解压缩流的代码页值。</span><span class="sxs-lookup"><span data-stu-id="10621-126">This is the code page value of the returned decompressed stream that you want.</span></span> <span data-ttu-id="10621-127">如果设置为非零值 [，WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) 函数会将流转换为指定的代码页。</span><span class="sxs-lookup"><span data-stu-id="10621-127">If this is set to a non-zero value, the [WrapCompressedRTFStreamEx](wrapcompressedrtfstreamex.md) function converts the stream to the specified code page.</span></span> <span data-ttu-id="10621-128">如果设置为零值，MAPI 将决定使用哪个代码页。</span><span class="sxs-lookup"><span data-stu-id="10621-128">If this is set to a zero value, MAPI decides which code page to use.</span></span> <span data-ttu-id="10621-129">只有在 _ulFlags_ 中传递 MAPI_NATIVE_BODY 标记且正文格式不是 RTF 时，才使用此值。</span><span class="sxs-lookup"><span data-stu-id="10621-129">This value is used only when the **MAPI_NATIVE_BODY** flag is passed in  _ulFlags_, and the body format is not RTF.</span></span> <span data-ttu-id="10621-130">否则，将忽略此值。</span><span class="sxs-lookup"><span data-stu-id="10621-130">Otherwise, this value is ignored.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="10621-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10621-131">See also</span></span>



[<span data-ttu-id="10621-132">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="10621-132">WrapCompressedRTFStreamEx</span></span>](wrapcompressedrtfstreamex.md)

