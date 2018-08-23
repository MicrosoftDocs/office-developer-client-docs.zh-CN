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
ms.openlocfilehash: f37d398167e8210a2fd67ff08e63572eb6c9db9c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585722"
---
# <a name="mapi-form-interfaces"></a>MAPI 表单接口

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
MAPI 定义以下与表单相关的接口。
  
|**接口名称**|**说明**|
|:-----|:-----|
|[IMAPIForm](imapiformiunknown.md) <br/> |处理表单对象并处理窗体对象命令。  <br/> |
|[IMAPIFormAdviseSink](imapiformadvisesinkiunknown.md) <br/> |确定是否 form 对象可以处理下一条消息，并更改 form 对象的一个或下一个状态。  <br/> |
|[IMAPIFormContainer](imapiformcontaineriunknown.md) <br/> |安装、 卸载和针对特定窗体容器的窗体服务器的解析支持。  <br/> |
|[IMAPIFormFactory](imapiformfactoryiunknown.md) <br/> |支持使用可配置的运行时窗体服务器。  <br/> |
|[IMAPIFormInfo](imapiforminfoimapiprop.md) <br/> |允许客户端应用程序使用的特定于邮件类的属性。  <br/> |
|[IMAPIFormMgr](imapiformmgriunknown.md) <br/> |启用客户端应用程序，以获取有关窗体服务器的信息、 激活窗体服务器，并将窗体服务器安装在邮件系统中。  <br/> |
|[IMAPIMessageSite](imapimessagesiteiunknown.md) <br/> |用来处理表单对象相关联的邮件。  <br/> |
|[IMAPIViewAdviseSink](imapiviewadvisesinkiunknown.md) <br/> |通知事件发生在窗体对象中的客户端应用程序。  <br/> |
|[IMAPIViewContext](imapiviewcontextiunknown.md) <br/> |用于响应窗体对象中的下一步、 上一步，和删除命令。  <br/> |
|[IPersistMessage](ipersistmessageiunknown.md) <br/> |用于保存、 初始化和加载窗体与邮件存储的对象。  <br/> |
   
MAPI 表单接口的方法的详细信息，请参阅这些接口的文档。 您不必实现的所有 MAPI 表单接口以创建自定义窗体。 窗体本身，只需实现**IPersistMessage**， **IMAPIForm**，以及**IMAPIFormAdviseSink**接口。 此外，它也是最好**IMAPIFormFactory**和**IMAPIFormInfo**实现。 用于 OLE 法规遵从性， **IMAPIFormFactory**并**IMAPIFormInfo**使编写完善的客户端应用程序能够更好地利用窗体。 
  
> [!NOTE]
> 严格来说， **IMAPIFormAdviseSink**是一个可选的接口。 但是，强烈建议在窗体服务器中实现。 该接口是非常重要的消息客户端和窗体服务器之间的有效交互尤其是当您的窗体服务器的多个邮件邮件类是所涉及的。 
  
## <a name="see-also"></a>另请参阅



[MAPI 表单](mapi-forms.md)

