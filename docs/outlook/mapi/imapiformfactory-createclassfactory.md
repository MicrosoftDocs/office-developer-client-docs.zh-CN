---
title: IMAPIFormFactoryCreateClassFactory
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormFactory.CreateClassFactory
api_type:
- COM
ms.assetid: dceb21b1-be5e-418d-b0c9-db39195fc82e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6e616a76d9665b602184e88566384506fcce5697
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416074"
---
# <a name="imapiformfactorycreateclassfactory"></a><span data-ttu-id="1429c-103">IMAPIFormFactory::CreateClassFactory</span><span class="sxs-lookup"><span data-stu-id="1429c-103">IMAPIFormFactory::CreateClassFactory</span></span>

  
  
<span data-ttu-id="1429c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1429c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1429c-105">返回窗体的类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="1429c-105">Returns a class factory object for the form.</span></span>
  
```cpp
HRESULT CreateClassFactory(
  REFCLSID clsidForm,
  ULONG ulFlags,
  LPCLASSFACTORY FAR * lppClassFactory
);
```

## <a name="parameters"></a><span data-ttu-id="1429c-106">参数</span><span class="sxs-lookup"><span data-stu-id="1429c-106">Parameters</span></span>

 <span data-ttu-id="1429c-107">_clsidForm_</span><span class="sxs-lookup"><span data-stu-id="1429c-107">_clsidForm_</span></span>
  
> <span data-ttu-id="1429c-108">[in]类工厂要创建的表单的类标识符。</span><span class="sxs-lookup"><span data-stu-id="1429c-108">[in] A class identifier for the form to be created by the class factory.</span></span>
    
 <span data-ttu-id="1429c-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1429c-109">_ulFlags_</span></span>
  
> <span data-ttu-id="1429c-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="1429c-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="1429c-111">_lppClassFactory_</span><span class="sxs-lookup"><span data-stu-id="1429c-111">_lppClassFactory_</span></span>
  
> <span data-ttu-id="1429c-112">[out]指向类工厂对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1429c-112">[out] A pointer to the class factory object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1429c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="1429c-113">Return value</span></span>

<span data-ttu-id="1429c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1429c-114">S_OK</span></span> 
  
> <span data-ttu-id="1429c-115">已返回类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="1429c-115">The class factory object was returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1429c-116">备注</span><span class="sxs-lookup"><span data-stu-id="1429c-116">Remarks</span></span>

<span data-ttu-id="1429c-117">表单查看器调用 **IMAPIFormFactory：：CreateClassFactory** 方法来获取特定表单的类工厂。</span><span class="sxs-lookup"><span data-stu-id="1429c-117">Form viewers call the **IMAPIFormFactory::CreateClassFactory** method to obtain a class factory for a specific form.</span></span> <span data-ttu-id="1429c-118">类工厂用于创建表单的实例，这些实例可处理特定类的消息，并控制对这些实例的访问。</span><span class="sxs-lookup"><span data-stu-id="1429c-118">The class factory is used to create instances of a form that handles messages of a specific class and to control the access to these instances.</span></span> 
  
<span data-ttu-id="1429c-119">表单 **查看器调用 CreateClassFactory** 方法以获取实现多个邮件类的表单服务器的类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="1429c-119">The **CreateClassFactory** method is called by form viewers to obtain a class factory object for form servers that implement multiple message classes.</span></span> <span data-ttu-id="1429c-120">此方法以参数 (CLSID) 类标识符。</span><span class="sxs-lookup"><span data-stu-id="1429c-120">This method receives a class identifier (CLSID) as a parameter.</span></span> <span data-ttu-id="1429c-121">基于该参数，此方法可以确定要返回的特定类工厂对象类型。</span><span class="sxs-lookup"><span data-stu-id="1429c-121">Based on that parameter, this method can determine the specific kind of class factory object to return.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="1429c-122">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="1429c-122">Notes to implementers</span></span>

<span data-ttu-id="1429c-123">对于同一类标识符的多个调用，可以从 **CreateClassFactory** 实现返回相同的类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="1429c-123">You can return from your **CreateClassFactory** implementation the same class factory object on multiple calls for the same class identifier.</span></span> <span data-ttu-id="1429c-124">不需要创建新的类工厂实例。</span><span class="sxs-lookup"><span data-stu-id="1429c-124">Creating a new class factory instance is not required.</span></span> 
  
<span data-ttu-id="1429c-125">您可以具有一个类工厂实现（可按需创建相应的类工厂实例）或多个类工厂实现（每个邮件类一个）。</span><span class="sxs-lookup"><span data-stu-id="1429c-125">You can have a single class factory implementation that creates appropriate class factory instances on demand, or multiple class factory implementations, one for each message class.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1429c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1429c-126">See also</span></span>



[<span data-ttu-id="1429c-127">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1429c-127">IMAPIFormFactory : IUnknown</span></span>](imapiformfactoryiunknown.md)

