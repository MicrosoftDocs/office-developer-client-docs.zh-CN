---
title: HexFromBin
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.HexFromBin
api_type:
- COM
ms.assetid: 12b95657-1926-4a24-be63-40305ea6f990
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1bf02de914865e27c8c018aba8695c858888ae2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412574"
---
# <a name="hexfrombin"></a><span data-ttu-id="a85b3-103">HexFromBin</span><span class="sxs-lookup"><span data-stu-id="a85b3-103">HexFromBin</span></span>

  
  
<span data-ttu-id="a85b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a85b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a85b3-105">将二进制数转换为十六进制数的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="a85b3-105">Converts a binary number into a string representation of a hexadecimal number.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a85b3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="a85b3-106">Header file:</span></span>  <br/> |<span data-ttu-id="a85b3-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="a85b3-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="a85b3-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="a85b3-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="a85b3-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="a85b3-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="a85b3-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="a85b3-110">Called by:</span></span>  <br/> |<span data-ttu-id="a85b3-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="a85b3-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void HexFromBin(
  LPBYTE pb,
  int cb,
  LPSTR sz
);
```

## <a name="parameters"></a><span data-ttu-id="a85b3-112">参数</span><span class="sxs-lookup"><span data-stu-id="a85b3-112">Parameters</span></span>

 <span data-ttu-id="a85b3-113">_pb_</span><span class="sxs-lookup"><span data-stu-id="a85b3-113">_pb_</span></span>
  
> <span data-ttu-id="a85b3-114">[in]指向要转换的二进制数据的指针。</span><span class="sxs-lookup"><span data-stu-id="a85b3-114">[in] Pointer to the binary data to be converted.</span></span> 
    
 <span data-ttu-id="a85b3-115">_cb_</span><span class="sxs-lookup"><span data-stu-id="a85b3-115">_cb_</span></span>
  
> <span data-ttu-id="a85b3-116">[in]pb 参数指向的二进制数据的大小（以  _字节_ 为单位）。</span><span class="sxs-lookup"><span data-stu-id="a85b3-116">[in] Size, in bytes, of the binary data pointed to by the  _pb_ parameter.</span></span> 
    
 <span data-ttu-id="a85b3-117">_sz_</span><span class="sxs-lookup"><span data-stu-id="a85b3-117">_sz_</span></span>
  
> <span data-ttu-id="a85b3-118">[out]指向以 null 结尾的 ASCII 字符串的指针，该字符串代表十六进制数字中的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="a85b3-118">[out] Pointer to a null-terminated ASCII string representing the binary data in hexadecimal digits.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a85b3-119">返回值</span><span class="sxs-lookup"><span data-stu-id="a85b3-119">Return value</span></span>

<span data-ttu-id="a85b3-120">无。</span><span class="sxs-lookup"><span data-stu-id="a85b3-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="a85b3-121">说明</span><span class="sxs-lookup"><span data-stu-id="a85b3-121">Remarks</span></span>

<span data-ttu-id="a85b3-122">**HexFromBin** 函数采用指向二进制数据单位的指针，其大小由 _cb_ 参数指示。</span><span class="sxs-lookup"><span data-stu-id="a85b3-122">The **HexFromBin** function takes a pointer to a unit of binary data whose size is indicated by the  _cb_ parameter.</span></span> <span data-ttu-id="a85b3-123">它在  _sz_ 字符串中返回， (2\*  _cb_) +1 字节的内存，以十六进制数表示此二进制信息。</span><span class="sxs-lookup"><span data-stu-id="a85b3-123">It returns in the  _sz_ string, within (2\*  _cb_)+1 bytes of memory, a representation of this binary information in hexadecimal numbers.</span></span> <span data-ttu-id="a85b3-124">例如，如果字节值为十进制 10，则十六进制字符串将为 0A，因此字符串中的一个字节转换为两个字节。</span><span class="sxs-lookup"><span data-stu-id="a85b3-124">If the byte value is decimal 10, for example, the hexadecimal string will be 0A, so one byte converts to two bytes in the string.</span></span> 
  

