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
ms.openlocfilehash: 4687b07c89d866acbe3b6a8f4cde3262657a06b5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584245"
---
# <a name="declaring-form-interfaces"></a><span data-ttu-id="4bb4b-103">声明表单接口</span><span class="sxs-lookup"><span data-stu-id="4bb4b-103">Declaring Form Interfaces</span></span>

  
  
<span data-ttu-id="4bb4b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4bb4b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4bb4b-105">还可以通过使用 MAPI_ _interface__METHOD 宏，其中_接口_在 Mapiform.h 标头文件中定义的窗体界面简化的 MAPI 表单接口实现的声明。</span><span class="sxs-lookup"><span data-stu-id="4bb4b-105">You can simplify the declarations of your implementations of MAPI form interfaces by using the MAPI_ _interface__METHOD macros, where  _interface_ is a form interface defined in the Mapiform.h header file.</span></span> <span data-ttu-id="4bb4b-106">您不需要使用这些宏，但如果您不应采取特别注意您声明符合 Mapiform.h 头文件中的声明。</span><span class="sxs-lookup"><span data-stu-id="4bb4b-106">You are not required to use these macros, but if you do not, you should take particular care that your declarations conform to the declarations in the Mapiform.h header file.</span></span> <span data-ttu-id="4bb4b-107">例如，您无法声明窗体服务器的窗体对象类，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4bb4b-107">For example, you could declare your form server's form object class like the following:</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="4bb4b-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bb4b-108">See also</span></span>



[<span data-ttu-id="4bb4b-109">编写表单服务器代码</span><span class="sxs-lookup"><span data-stu-id="4bb4b-109">Writing Form Server Code</span></span>](writing-form-server-code.md)

