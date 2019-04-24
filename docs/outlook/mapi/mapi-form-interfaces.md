---
title: MAPI 表单接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 611213c9-e758-4366-b193-fc62181d3d1f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f207f9550c61ad69fd1fc560cdb2084b7bb56c6f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351539"
---
# <a name="mapi-form-interfaces"></a>MAPI 表单接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义了与表单相关的下列接口。
  
|**接口名称**|**Description**|
|:-----|:-----|
|[IMAPIForm](imapiformiunknown.md) <br/> |操纵窗体对象并处理窗体对象命令。  <br/> |
|[IMAPIFormAdviseSink](imapiformadvisesinkiunknown.md) <br/> |确定窗体对象是否可以处理下一封邮件, 并更改该窗体对象的下一个或上一个状态。  <br/> |
|[IMAPIFormContainer](imapiformcontaineriunknown.md) <br/> |支持针对特定表单容器安装、卸载和解析表单服务器。  <br/> |
|[IMAPIFormFactory](imapiformfactoryiunknown.md) <br/> |支持使用可配置的运行时窗体服务器。  <br/> |
|[IMAPIFormInfo](imapiforminfoimapiprop.md) <br/> |使客户端应用程序能够使用特定于邮件类的属性。  <br/> |
|[IMAPIFormMgr](imapiformmgriunknown.md) <br/> |使客户端应用程序能够获取有关表单服务器、激活表单服务器和在邮件系统中安装表单服务器的信息。  <br/> |
|[IMAPIMessageSite](imapimessagesiteiunknown.md) <br/> |用于操作与表单对象相关联的邮件。  <br/> |
|[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) <br/> |通知客户端应用程序表单对象中发生了事件。  <br/> |
|[IMAPIViewContext](imapiviewcontextiunknown.md) <br/> |用于响应 form 对象中的下一个、上一个和删除命令。  <br/> |
|[IPersistMessage](ipersistmessageiunknown.md) <br/> |用于在邮件存储中保存、初始化和加载 form 对象。  <br/> |
   
有关 MAPI 表单接口的方法的详细信息, 请参阅这些接口的文档。 您无需实现所有 MAPI 表单接口即可创建自定义窗体。 窗体本身只需要实现**IPersistMessage**、 **IMAPIForm**和**IMAPIFormAdviseSink**接口。 此外, 还最好实现**IMAPIFormFactory**和**IMAPIFormInfo**。 **IMAPIFormFactory**对于 OLE 合规性非常有用, **IMAPIFormInfo**支持编写完善的客户端应用程序, 以便更好地使用表单。 
  
> [!NOTE]
> 严格来说, **IMAPIFormAdviseSink**是一个可选接口。 但是, 强烈建议您在表单服务器中实现它。 此接口对于在邮件客户端和窗体服务器之间进行有效交互非常关键, 尤其是当处理多个窗体服务器的邮件类的邮件时。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

