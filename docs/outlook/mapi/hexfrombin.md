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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299459"
---
# <a name="hexfrombin"></a><span data-ttu-id="ad716-103">HexFromBin</span><span class="sxs-lookup"><span data-stu-id="ad716-103">HexFromBin</span></span>

  
  
<span data-ttu-id="ad716-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad716-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad716-105">将二进制数转换为十六进制数的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="ad716-105">Converts a binary number into a string representation of a hexadecimal number.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ad716-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ad716-106">Header file:</span></span>  <br/> |<span data-ttu-id="ad716-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="ad716-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="ad716-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ad716-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ad716-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ad716-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ad716-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ad716-110">Called by:</span></span>  <br/> |<span data-ttu-id="ad716-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="ad716-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
void HexFromBin(
  LPBYTE pb,
  int cb,
  LPSTR sz
);
```

## <a name="parameters"></a><span data-ttu-id="ad716-112">参数</span><span class="sxs-lookup"><span data-stu-id="ad716-112">Parameters</span></span>

 <span data-ttu-id="ad716-113">_pb_</span><span class="sxs-lookup"><span data-stu-id="ad716-113">_pb_</span></span>
  
> <span data-ttu-id="ad716-114">实时指向要转换的二进制数据的指针。</span><span class="sxs-lookup"><span data-stu-id="ad716-114">[in] Pointer to the binary data to be converted.</span></span> 
    
 <span data-ttu-id="ad716-115">_cb_</span><span class="sxs-lookup"><span data-stu-id="ad716-115">_cb_</span></span>
  
> <span data-ttu-id="ad716-116">实时_pb_参数指向的二进制数据的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ad716-116">[in] Size, in bytes, of the binary data pointed to by the  _pb_ parameter.</span></span> 
    
 <span data-ttu-id="ad716-117">_sz_</span><span class="sxs-lookup"><span data-stu-id="ad716-117">_sz_</span></span>
  
> <span data-ttu-id="ad716-118">排除指向以十六进制数字表示二进制数据的以 null 结尾的 ASCII 字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="ad716-118">[out] Pointer to a null-terminated ASCII string representing the binary data in hexadecimal digits.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ad716-119">返回值</span><span class="sxs-lookup"><span data-stu-id="ad716-119">Return value</span></span>

<span data-ttu-id="ad716-120">无。</span><span class="sxs-lookup"><span data-stu-id="ad716-120">None.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ad716-121">注解</span><span class="sxs-lookup"><span data-stu-id="ad716-121">Remarks</span></span>

<span data-ttu-id="ad716-122">**HexFromBin**函数获取指向二进制数据单位的指针, 该数据单位的大小由_cb_参数指示。</span><span class="sxs-lookup"><span data-stu-id="ad716-122">The **HexFromBin** function takes a pointer to a unit of binary data whose size is indicated by the  _cb_ parameter.</span></span> <span data-ttu-id="ad716-123">它在_sz_字符串中返回 (2 \* _cb_) + 1 字节的内存, 这是十六进制数中的此二进制信息的表示形式。</span><span class="sxs-lookup"><span data-stu-id="ad716-123">It returns in the  _sz_ string, within (2\*  _cb_)+1 bytes of memory, a representation of this binary information in hexadecimal numbers.</span></span> <span data-ttu-id="ad716-124">例如, 如果字节值为十进制数 10, 则十六进制字符串将为 0A, 因此一个字节将转换为字符串中的两个字节。</span><span class="sxs-lookup"><span data-stu-id="ad716-124">If the byte value is decimal 10, for example, the hexadecimal string will be 0A, so one byte converts to two bytes in the string.</span></span> 
  

