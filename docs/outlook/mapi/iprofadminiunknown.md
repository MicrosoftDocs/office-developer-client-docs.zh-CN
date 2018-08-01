---
title: IProfAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin
api_type:
- COM
ms.assetid: 274899cc-2894-4d99-84ec-f18121e856a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c6192e6f92078f2f9bab0d55e9952d21ebb82af6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776005"
---
# <a name="iprofadmin--iunknown"></a>IProfAdmin : IUnknown

  
  
**适用于**： Outlook 
  
支持配置文件的管理。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|由公开：  <br/> |配置文件管理对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IProfAdmin  <br/> |
|指针类型：  <br/> |LPPROFADMIN  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[时出错](iprofadmin-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的配置文件管理对象发生的错误的信息。  <br/> |
|[GetProfileTable](iprofadmin-getprofiletable.md) <br/> |提供对配置文件表中，一个表，包含有关所有可用的配置文件信息的访问。  <br/> |
|[CreateProfile](iprofadmin-createprofile.md) <br/> |创建新的配置文件。  <br/> |
|[DeleteProfile](iprofadmin-deleteprofile.md) <br/> |删除配置文件。  <br/> |
|[ChangeProfilePassword](iprofadmin-changeprofilepassword.md) <br/> |已弃用。 更改配置文件的密码。  <br/> |
|[CopyProfile](iprofadmin-copyprofile.md) <br/> |一个配置文件的副本。  <br/> |
|[RenameProfile](iprofadmin-renameprofile.md) <br/> |向一个配置文件分配一个新名称。  <br/> |
|[SetDefaultProfile](iprofadmin-setdefaultprofile.md) <br/> |设置或清除客户端的默认配置文件。  <br/> |
|[AdminServices](iprofadmin-adminservices.md) <br/> |提供对邮件服务管理对象的更改配置文件中的消息服务的访问。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

