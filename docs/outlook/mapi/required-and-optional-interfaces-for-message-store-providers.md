---
title: 邮件存储提供程序的必需接口和可选接口
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc62e57e-82a4-4f37-8d1b-7cdf828b951e
description: 上次修改时间：2015 年 12 月 7 日
ms.openlocfilehash: 35b1d05d742b0d8defabf84b6dbf7d418ece0bbd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420918"
---
# <a name="required-and-optional-interfaces-for-message-store-providers"></a>邮件存储提供程序的必需接口和可选接口

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 定义一组与邮件存储提供程序相关的接口。 由于邮件存储可以选择实现各种功能，因此其中一些接口是必需的，有些则不是。 下表列出了与邮件存储提供程序相关的 MAPI 接口，指定了这些接口是必需接口还是可选接口，并描述了它们的用途。
  
|**接口**|**状态**|**说明**|
|:-----|:-----|:-----|
|[IMSProvider](imsprovideriunknown.md) <br/> |必需  <br/> |登录到和注销邮件存储。  <br/> |
|[IMSLogon](imslogoniunknown.md) <br/> |必需  <br/> |打开文件夹或邮件，验证邮件存储的标识并处理通知。  <br/> |
|[IMsgStore](imsgstoreimapiprop.md) <br/> |必需  <br/> |打开文件夹或邮件，查找特殊文件夹，并处理邮件提交。  <br/> |
|[IMAPIFolder](imapifolderimapicontainer.md) <br/> |必需  <br/> |查找和处理消息和子文件夹。  <br/> |
|[IMessage](imessageimapiprop.md) <br/> |必需  <br/> |操作附件并设置邮件的一些属性。  <br/> |
|[IMAPITable](imapitableiunknown.md) <br/> |必需  <br/> |允许其他对象向各种 MAPI 组件显示数据集合。  <br/> |
|[IMAPIStatus](imapistatusimapiprop.md) <br/> |必需  <br/> |使客户端能够验证邮件存储的状态并执行一些配置任务。  <br/> |
|[IAttach](iattachimapiprop.md) <br/> |可选  <br/> |如果存储提供程序支持文件附件，则访问邮件附件属性。  <br/> |
|**IStorage** <br/> |可选  <br/> |如果存储提供程序支持 OLE 对象附件，则管理结构化存储对象。  <br/> |
|**IStream** <br/> |可选  <br/> |使邮件和附件对象能够读取数据以及将数据写入流对象。  <br/> |
|**IStreamDocfile** <br/> |可选  <br/> |允许某些服务提供商打开存储对象，例如 OLE 2.0 文件格式的复合文件。  <br/> |
   
这些接口的参考主题中记录了实现 IMAPIFolder、IMessage、IMAPIStatus 和 **IMAPITable** 所需的基本信息。    本节包含与邮件存储提供程序更直接相关的补充信息。 其余 MAPI 接口应按照本节和相应参考主题的信息实现。 有关实现 **IStorage、IStream** 和 **IStreamDocFile** Windows，请参阅 Windows SDK 中的COM 和 ActiveX 对象服务部分。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 邮件存储提供程序](developing-a-mapi-message-store-provider.md)

