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
# <a name="implementing-the-iclassfactory-interface-for-form-servers"></a>为表单服务器实现 IClassFactory 接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
[IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx) 是客户端应用程序用于创建表单服务器的邮件类的新表单对象的 OLE 接口。 下表列出了所需的 **IClassFactory** 方法。 
  
|**方法**|**说明**|
|:-----|:-----|
|[CreateInstance](https://msdn.microsoft.com/library/ms682215%28v=VS.85%29.aspx) <br/> |创建新的窗体对象。  <br/> |
|[LockServer](https://msdn.microsoft.com/library/ms682332%28v=VS.85%29.aspx) <br/> |锁定内存中的窗体服务器，以避免创建多个表单对象时出现启动开销。  <br/> |
   
有关实现这些方法所需的全部信息，请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务部分。
  
## <a name="see-also"></a>另请参阅



[编写表单服务器代码](writing-form-server-code.md)

