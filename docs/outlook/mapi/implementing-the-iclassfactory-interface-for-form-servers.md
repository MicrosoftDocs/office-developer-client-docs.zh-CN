---
title: 实现表单服务器的 IClassFactory 接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22402261-c0fc-49bd-a222-e31989d6ff30
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ecae23d8631c818fb3d1c6786b2d180e9f32a2e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775821"
---
# <a name="implementing-the-iclassfactory-interface-for-form-servers"></a>实现表单服务器的 IClassFactory 接口

  
  
**适用于**： Outlook 
  
[IClassFactory](http://msdn.microsoft.com/en-us/library/ms694364%28VS.85%29.aspx)是客户端应用程序用于创建窗体服务器的邮件类的新表单对象的 OLE 接口。 下表列出了所需的**IClassFactory**方法。 
  
|**方法**|**说明**|
|:-----|:-----|
|[创建实例](http://msdn.microsoft.com/en-us/library/ms682215%28v=VS.85%29.aspx) <br/> |创建一个新的窗体对象。  <br/> |
|[LockServer](http://msdn.microsoft.com/en-us/library/ms682332%28v=VS.85%29.aspx) <br/> |锁定的窗体服务器内存中，以便创建多个窗体对象时，可以避免启动开销。  <br/> |
   
有关所有所需的信息实现这些方法，请参阅 Windows SDK 中的 COM 和 ActiveX 对象服务一节。
  
## <a name="see-also"></a>另请参阅



[编写表单服务器代码](writing-form-server-code.md)

