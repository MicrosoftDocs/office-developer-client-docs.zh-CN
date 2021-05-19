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
  
> [in]类工厂要创建的表单的类标识符。
    
 _ulFlags_
  
> [in]保留;必须为零。
    
 _lppClassFactory_
  
> [out]指向类工厂对象的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已返回类工厂对象。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormFactory：：CreateClassFactory** 方法来获取特定表单的类工厂。 类工厂用于创建表单的实例，这些实例可处理特定类的消息，并控制对这些实例的访问。 
  
表单 **查看器调用 CreateClassFactory** 方法以获取实现多个邮件类的表单服务器的类工厂对象。 此方法以参数 (CLSID) 类标识符。 基于该参数，此方法可以确定要返回的特定类工厂对象类型。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

对于同一类标识符的多个调用，可以从 **CreateClassFactory** 实现返回相同的类工厂对象。 不需要创建新的类工厂实例。 
  
您可以具有一个类工厂实现（可按需创建相应的类工厂实例）或多个类工厂实现（每个邮件类一个）。
  
## <a name="see-also"></a>另请参阅



[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md)

