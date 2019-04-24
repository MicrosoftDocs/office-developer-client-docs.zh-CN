---
title: ISocialPersonGetPicture
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 02fcaf25-42b5-4584-95c6-d44a3d035128
description: 获取包含人员的图片资源的字节数组。
ms.openlocfilehash: 755e2138378136a3c1d810a1957923f4e8db721d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331652"
---
# <a name="isocialpersongetpicture"></a><span data-ttu-id="4d739-103">ISocialPerson::GetPicture</span><span class="sxs-lookup"><span data-stu-id="4d739-103">ISocialPerson::GetPicture</span></span>

<span data-ttu-id="4d739-104">获取包含人员的图片资源的字节数组。</span><span class="sxs-lookup"><span data-stu-id="4d739-104">Gets an array of bytes that contains the picture resource for the person.</span></span> 
  
```cpp
HRESULT _stdcall GetPicture([out, retval] SAFEARRAY(unsigned char)* picture);
```

## <a name="parameters"></a><span data-ttu-id="4d739-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d739-105">Parameters</span></span>

<span data-ttu-id="4d739-106">_头像_</span><span class="sxs-lookup"><span data-stu-id="4d739-106">_picture_</span></span>
  
> <span data-ttu-id="4d739-107">排除指向结构的指针, 该结构指定代表人员的图片资源的字节数组。</span><span class="sxs-lookup"><span data-stu-id="4d739-107">[out] A pointer to a structure that specifies an array of bytes that represent the picture resource for a person.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4d739-108">注解</span><span class="sxs-lookup"><span data-stu-id="4d739-108">Remarks</span></span>

<span data-ttu-id="4d739-109">支持的图片资源采用 .bmp、jpeg 或 .png 格式。</span><span class="sxs-lookup"><span data-stu-id="4d739-109">Supported picture resources are in .bmp, .jpeg, or .png format.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d739-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d739-110">See also</span></span>

- [<span data-ttu-id="4d739-111">ISocialPerson : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4d739-111">ISocialPerson : IUnknown</span></span>](isocialpersoniunknown.md)

