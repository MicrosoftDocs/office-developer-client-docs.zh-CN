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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342173"
---
# <a name="imapiformfactorycreateclassfactory"></a>IMAPIFormFactory::CreateClassFactory

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回窗体的类工厂对象。
  
```cpp
HRESULT CreateClassFactory(
  REFCLSID clsidForm,
  ULONG ulFlags,
  LPCLASSFACTORY FAR * lppClassFactory
);
```

## <a name="parameters"></a>参数

 _clsidForm_
  
> 实时要由类工厂创建的表单的类标识符。
    
 _ulFlags_
  
> 实时保留必须为零。
    
 _lppClassFactory_
  
> 排除指向类工厂对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 返回了 class factory 对象。
    
## <a name="remarks"></a>注解

表单查看者调用**IMAPIFormFactory:: CreateClassFactory**方法以获取特定窗体的类工厂。 类工厂用于创建处理特定类的邮件并控制对这些实例的访问权限的表单的实例。 
  
表单查看器调用**CreateClassFactory**方法, 以获取实现多个邮件类的表单服务器的类工厂对象。 此方法接收类标识符 (CLSID) 作为参数。 根据该参数, 此方法可以确定要返回的类工厂对象的特定种类。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

您可以从您的**CreateClassFactory**实现对同一类标识符的多个调用返回相同的类工厂对象。 不需要创建新的类工厂实例。 
  
您可以具有单个类工厂实现, 该实现根据需要创建相应的类工厂实例, 或者具有多个类工厂实现, 每个邮件类一个实现。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md)

