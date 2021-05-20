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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437509"
---
# <a name="declaring-form-interfaces"></a>声明表单接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
可以使用 MAPI_ _interface__METHOD 宏简化 MAPI 表单接口实现的声明，其中  _interface_ 是在 Mapiform.h 头文件中定义的窗体接口。 虽然不需要使用这些宏，但如果不这样做，应特别注意声明是否符合 Mapiform.h 头文件中的声明。 例如，可以声明表单服务器的 form 对象类，如下所示： 
  
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

