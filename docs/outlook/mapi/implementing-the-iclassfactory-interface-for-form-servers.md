---
title: 为表单服务器实现 IClassFactory 接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22402261-c0fc-49bd-a222-e31989d6ff30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 12d854b72632653d9e1081c9e726c0fe7087bc27
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310029"
---
# <a name="implementing-the-iclassfactory-interface-for-form-servers"></a><span data-ttu-id="ba9d0-103">为表单服务器实现 IClassFactory 接口</span><span class="sxs-lookup"><span data-stu-id="ba9d0-103">Implementing the IClassFactory Interface for Form Servers</span></span>

  
  
<span data-ttu-id="ba9d0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ba9d0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ba9d0-105">[IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx)是客户端应用程序用于创建表单服务器的邮件类的新表单对象的 OLE 接口。</span><span class="sxs-lookup"><span data-stu-id="ba9d0-105">[IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx) is the OLE interface that client applications use to create new form objects of your form server's message class.</span></span> <span data-ttu-id="ba9d0-106">下表列出了所需的**IClassFactory**方法。</span><span class="sxs-lookup"><span data-stu-id="ba9d0-106">The following table lists the **IClassFactory** methods that are required.</span></span> 
  
|<span data-ttu-id="ba9d0-107">**方法**</span><span class="sxs-lookup"><span data-stu-id="ba9d0-107">**Method**</span></span>|<span data-ttu-id="ba9d0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ba9d0-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ba9d0-109">CreateInstance</span><span class="sxs-lookup"><span data-stu-id="ba9d0-109">CreateInstance</span></span>](https://msdn.microsoft.com/library/ms682215%28v=VS.85%29.aspx) <br/> |<span data-ttu-id="ba9d0-110">创建新的表单对象。</span><span class="sxs-lookup"><span data-stu-id="ba9d0-110">Creates a new form object.</span></span>  <br/> |
|[<span data-ttu-id="ba9d0-111">LockServer</span><span class="sxs-lookup"><span data-stu-id="ba9d0-111">LockServer</span></span>](https://msdn.microsoft.com/library/ms682332%28v=VS.85%29.aspx) <br/> |<span data-ttu-id="ba9d0-112">锁定内存中的窗体服务器, 以便在创建多个窗体对象时可以避免启动开销。</span><span class="sxs-lookup"><span data-stu-id="ba9d0-112">Locks the form server in memory so that startup overhead can be avoided when multiple form objects are created.</span></span>  <br/> |
   
<span data-ttu-id="ba9d0-113">有关实现这些方法所需的所有信息, 请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务一节。</span><span class="sxs-lookup"><span data-stu-id="ba9d0-113">For all the information necessary to implement these methods, see the COM and ActiveX Object Services section in the Windows SDK.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ba9d0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba9d0-114">See also</span></span>



[<span data-ttu-id="ba9d0-115">编写表单服务器代码</span><span class="sxs-lookup"><span data-stu-id="ba9d0-115">Writing Form Server Code</span></span>](writing-form-server-code.md)

