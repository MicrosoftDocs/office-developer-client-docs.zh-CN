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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412343"
---
# <a name="mapi-form-interfaces"></a>MAPI 表单接口

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义以下与表单相关的接口。
  
|**接口名称**|**说明**|
|:-----|:-----|
|[IMAPIForm](imapiformiunknown.md) <br/> |操作窗体对象并处理窗体对象命令。  <br/> |
|[IMAPIFormAdviseSink](imapiformadvisesinkiunknown.md) <br/> |确定 form 对象能否处理下一封邮件并更改窗体对象的下一个或上一状态。  <br/> |
|[IMAPIFormContainer](imapiformcontaineriunknown.md) <br/> |支持针对特定表单容器安装、取消安装和解析表单服务器。  <br/> |
|[IMAPIFormFactory](imapiformfactoryiunknown.md) <br/> |支持使用可配置的运行时表单服务器。  <br/> |
|[IMAPIFormInfo](imapiforminfoimapiprop.md) <br/> |使客户端应用程序能够使用特定于邮件类的属性。  <br/> |
|[IMAPIFormMgr](imapiformmgriunknown.md) <br/> |使客户端应用程序能够获取有关表单服务器的信息、激活表单服务器，以及安装邮件系统中表单服务器。  <br/> |
|[IMAPIMessageSite](imapimessagesiteiunknown.md) <br/> |用于处理与表单对象关联的邮件。  <br/> |
|[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) <br/> |通知客户端应用程序表单对象中已发生事件。  <br/> |
|[IMAPIViewContext](imapiviewcontextiunknown.md) <br/> |用于响应窗体对象中的 Next、Previous 和 Delete 命令。  <br/> |
|[IPersistMessage](ipersistmessageiunknown.md) <br/> |用于在邮件存储中保存、初始化和加载表单对象。  <br/> |
   
有关 MAPI 表单接口的方法详细信息，请参阅这些接口的文档。 您不一定非要实现所有 MAPI 窗体接口才能创建自定义窗体。 表单本身仅要求您实现 **IPersistMessage、IMAPIForm** 和 **IMAPIFormAdviseSink** 接口。  此外，实现 **IMAPIFormFactory** 和 **IMAPIFormInfo 也是一个好主意**。 **IMAPIFormFactory** 对于 OLE 合规性非常有用 **，IMAPIFormInfo** 使编写良好的客户端应用程序能够更好地利用表单。 
  
> [!NOTE]
> 严格来说 **，IMAPIFormAdviseSink** 是可选接口。 但是，强烈建议在表单服务器中实现它。 此接口对于邮件客户端和表单服务器之间的高效交互至关重要，尤其是在处理表单服务器的邮件类的几个消息时。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

