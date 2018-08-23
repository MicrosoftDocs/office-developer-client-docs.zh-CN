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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cb5cb5a0169e716f7fcc7f596660bc0222c51c84
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572156"
---
# <a name="imapiformfactorycreateclassfactory"></a><span data-ttu-id="bbbd2-103">IMAPIFormFactory::CreateClassFactory</span><span class="sxs-lookup"><span data-stu-id="bbbd2-103">IMAPIFormFactory::CreateClassFactory</span></span>

  
  
<span data-ttu-id="bbbd2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bbbd2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bbbd2-105">返回窗体类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-105">Returns a class factory object for the form.</span></span>
  
```cpp
HRESULT CreateClassFactory(
  REFCLSID clsidForm,
  ULONG ulFlags,
  LPCLASSFACTORY FAR * lppClassFactory
);
```

## <a name="parameters"></a><span data-ttu-id="bbbd2-106">参数</span><span class="sxs-lookup"><span data-stu-id="bbbd2-106">Parameters</span></span>

 <span data-ttu-id="bbbd2-107">_clsidForm_</span><span class="sxs-lookup"><span data-stu-id="bbbd2-107">_clsidForm_</span></span>
  
> <span data-ttu-id="bbbd2-108">[in]要创建的类工厂的表单类标识符。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-108">[in] A class identifier for the form to be created by the class factory.</span></span>
    
 <span data-ttu-id="bbbd2-109">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bbbd2-109">_ulFlags_</span></span>
  
> <span data-ttu-id="bbbd2-110">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-110">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="bbbd2-111">_lppClassFactory_</span><span class="sxs-lookup"><span data-stu-id="bbbd2-111">_lppClassFactory_</span></span>
  
> <span data-ttu-id="bbbd2-112">[输出]指向类工厂对象的指针。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-112">[out] A pointer to the class factory object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bbbd2-113">返回值</span><span class="sxs-lookup"><span data-stu-id="bbbd2-113">Return value</span></span>

<span data-ttu-id="bbbd2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="bbbd2-114">S_OK</span></span> 
  
> <span data-ttu-id="bbbd2-115">返回类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-115">The class factory object was returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bbbd2-116">注解</span><span class="sxs-lookup"><span data-stu-id="bbbd2-116">Remarks</span></span>

<span data-ttu-id="bbbd2-117">表单查看器调用**IMAPIFormFactory::CreateClassFactory**方法以获取特定窗体类工厂。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-117">Form viewers call the **IMAPIFormFactory::CreateClassFactory** method to obtain a class factory for a specific form.</span></span> <span data-ttu-id="bbbd2-118">类工厂用于创建窗体处理邮件的特定类的实例并控制对这些实例的访问。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-118">The class factory is used to create instances of a form that handles messages of a specific class and to control the access to these instances.</span></span> 
  
<span data-ttu-id="bbbd2-119">表单查看器获取类实现多个邮件类的窗体服务器中心对象调用**CreateClassFactory**方法。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-119">The **CreateClassFactory** method is called by form viewers to obtain a class factory object for form servers that implement multiple message classes.</span></span> <span data-ttu-id="bbbd2-120">此方法用作参数接收的类标识符 (CLSID)。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-120">This method receives a class identifier (CLSID) as a parameter.</span></span> <span data-ttu-id="bbbd2-121">基于该参数，此方法可以确定要返回的类中心对象的特定类型。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-121">Based on that parameter, this method can determine the specific kind of class factory object to return.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="bbbd2-122">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="bbbd2-122">Notes to implementers</span></span>

<span data-ttu-id="bbbd2-123">您可以从返回**CreateClassFactory**实现的相同的类工厂对象上的相同的类标识符的多个呼叫。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-123">You can return from your **CreateClassFactory** implementation the same class factory object on multiple calls for the same class identifier.</span></span> <span data-ttu-id="bbbd2-124">不需要创建新的类工厂实例。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-124">Creating a new class factory instance is not required.</span></span> 
  
<span data-ttu-id="bbbd2-125">您可以创建按需，合适的类工厂实例的单个类工厂实现或多个类工厂实现，一个用于每个邮件类。</span><span class="sxs-lookup"><span data-stu-id="bbbd2-125">You can have a single class factory implementation that creates appropriate class factory instances on demand, or multiple class factory implementations, one for each message class.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbbd2-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbbd2-126">See also</span></span>



[<span data-ttu-id="bbbd2-127">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bbbd2-127">IMAPIFormFactory : IUnknown</span></span>](imapiformfactoryiunknown.md)

