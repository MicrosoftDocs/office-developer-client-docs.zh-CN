---
title: 声明表单接口
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79283301-e544-4a4d-96c2-3f81dc5b3731
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 8f4d8842efbba2f1f2b7281e5d4741b89f975b3f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774749"
---
# <a name="declaring-form-interfaces"></a>声明表单接口

  
  
**适用于**： Outlook 
  
还可以通过使用 MAPI_ _interface__METHOD 宏，其中_接口_在 Mapiform.h 标头文件中定义的窗体界面简化的 MAPI 表单接口实现的声明。 您不需要使用这些宏，但如果您不应采取特别注意您声明符合 Mapiform.h 头文件中的声明。 例如，您无法声明窗体服务器的窗体对象类，如下所示： 
  
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

