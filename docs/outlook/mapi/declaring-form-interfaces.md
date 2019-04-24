---
title: 声明表单接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79283301-e544-4a4d-96c2-3f81dc5b3731
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 0fa742b7ff6d98e3a0f475accbc440d22eac0919
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337056"
---
# <a name="declaring-form-interfaces"></a>声明表单接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
您可以通过使用 MAPI_ _interface__METHOD 宏 (其中_接口_是在 Mapiform 头文件中定义的窗体接口) 简化您的 MAPI 表单接口实现的声明。 您不需要使用这些宏, 但如果您不是这样, 则应特别注意您的声明符合 Mapiform 头文件中的声明。 例如, 您可以声明窗体服务器的窗体对象类, 如下所示: 
  
```cpp
class CMyForm : public IPersistMessage, public IMAPIForm,
                public IMAPIFormAdviseSink
{
public:
    CMyForm(CClassFactory *);    // constructorr takes a class factory object
    ~CMyForm(void);
// MAPI methods that need to be implemented.
    MAPI_IUNKNOWN_METHODS(IMPL);
    MAPI_GETLASTERROR_METHOD(IMPL);
    MAPI_IPERSISTMESSAGE_METHODS(IMPL);
    MAPI_IMAPIFORM_METHODS(IMPL);
    MAPI_IMAPIFORMADVISESINK_METHODS(IMPL);
// Add other implementation specific items.
};

```

## <a name="see-also"></a>另请参阅



[编写表单服务器代码](writing-form-server-code.md)

