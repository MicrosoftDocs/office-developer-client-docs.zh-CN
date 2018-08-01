---
title: IID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.IID
api_type:
- COM
ms.assetid: fa5498ab-2f8a-42f8-ba9d-1d555768594f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a0e859ac0f8bcc3bd83e336c85da21f1251efcb5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775303"
---
# <a name="iid"></a><span data-ttu-id="e25ac-103">IID</span><span class="sxs-lookup"><span data-stu-id="e25ac-103">IID</span></span>

  
  
<span data-ttu-id="e25ac-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e25ac-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e25ac-105">介绍用于描述 MAPI 接口的标识符的[GUID](guid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e25ac-105">Describes a [GUID](guid.md) structure used to describe an identifier for a MAPI interface.</span></span> 
  
```cpp
typedef struct _GUID
{
  unsigned long Data1;
  unsigned short Data2;
  unsigned short Data3;
  unsigned char Data4[8];
} GUID;

```

## <a name="members"></a><span data-ttu-id="e25ac-106">Members</span><span class="sxs-lookup"><span data-stu-id="e25ac-106">Members</span></span>

<span data-ttu-id="e25ac-107">请参阅**GUID**结构。</span><span class="sxs-lookup"><span data-stu-id="e25ac-107">See the **GUID** structure.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="e25ac-108">说明</span><span class="sxs-lookup"><span data-stu-id="e25ac-108">Remarks</span></span>

<span data-ttu-id="e25ac-109">**IID**结构用于唯一标识 MAPI 接口并将特定接口与对象相关联。</span><span class="sxs-lookup"><span data-stu-id="e25ac-109">An **IID** structure is used to uniquely identify a MAPI interface and to associate a particular interface with an object.</span></span> <span data-ttu-id="e25ac-110">例如，当打开一个文件夹客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md) ，客户端将_lpInterface_参数设置为指向**IID**表示[IMAPIFolder](imapifolderimapicontainer.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e25ac-110">For example, when a client calls [IMAPISession::OpenEntry](imapisession-openentry.md) to open a folder, the client sets the  _lpInterface_ parameter to point to an **IID** representing the [IMAPIFolder](imapifolderimapicontainer.md) interface.</span></span> <span data-ttu-id="e25ac-111">MAPI 定义**IMAPIFolderIID**为 IID_IMAPIFolder。</span><span class="sxs-lookup"><span data-stu-id="e25ac-111">MAPI defines the **IMAPIFolderIID** to be IID_IMAPIFolder.</span></span> <span data-ttu-id="e25ac-112">**IID**结构还用于唯一标识 OLE 接口。</span><span class="sxs-lookup"><span data-stu-id="e25ac-112">**IID** structures are also used to uniquely identify OLE interfaces.</span></span> 
  
<span data-ttu-id="e25ac-113">所有的 MAPI 接口的特定**IID**结构 Mapiguid.h 头文件中定义。</span><span class="sxs-lookup"><span data-stu-id="e25ac-113">All of the specific **IID** structures for the MAPI interfaces are defined in the Mapiguid.h header file.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e25ac-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e25ac-114">See also</span></span>



[<span data-ttu-id="e25ac-115">GUID</span><span class="sxs-lookup"><span data-stu-id="e25ac-115">GUID</span></span>](guid.md)


[<span data-ttu-id="e25ac-116">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="e25ac-116">MAPI Structures</span></span>](mapi-structures.md)

