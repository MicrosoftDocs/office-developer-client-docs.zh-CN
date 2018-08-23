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
# <a name="imapiformfactorycreateclassfactory"></a>IMAPIFormFactory::CreateClassFactory

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回窗体类工厂对象。
  
```cpp
HRESULT CreateClassFactory(
  REFCLSID clsidForm,
  ULONG ulFlags,
  LPCLASSFACTORY FAR * lppClassFactory
);
```

## <a name="parameters"></a>参数

 _clsidForm_
  
> [in]要创建的类工厂的表单类标识符。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lppClassFactory_
  
> [输出]指向类工厂对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 返回类工厂对象。
    
## <a name="remarks"></a>注解

表单查看器调用**IMAPIFormFactory::CreateClassFactory**方法以获取特定窗体类工厂。 类工厂用于创建窗体处理邮件的特定类的实例并控制对这些实例的访问。 
  
表单查看器获取类实现多个邮件类的窗体服务器中心对象调用**CreateClassFactory**方法。 此方法用作参数接收的类标识符 (CLSID)。 基于该参数，此方法可以确定要返回的类中心对象的特定类型。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

您可以从返回**CreateClassFactory**实现的相同的类工厂对象上的相同的类标识符的多个呼叫。 不需要创建新的类工厂实例。 
  
您可以创建按需，合适的类工厂实例的单个类工厂实现或多个类工厂实现，一个用于每个邮件类。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md)

