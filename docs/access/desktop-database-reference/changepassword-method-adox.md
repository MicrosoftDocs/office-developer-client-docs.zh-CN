---
title: ChangePassword 方法 (ADOX)
TOCTitle: ChangePassword method (ADOX)
ms:assetid: 999826a5-3e6b-b6da-b8f6-d61b9a50ceca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249690(v=office.15)
ms:contentKeyID: 48546519
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e7e6d88b207fecc93b9a9bafa2d6b504456a3a3e
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949269"
---
# <a name="changepassword-method-adox"></a>ChangePassword 方法 (ADOX)

**适用于**： Access 2013、 Office 2013

更改用户帐户的密码。

## <a name="syntax"></a>语法

*用户*。ChangePassword*旧密码* *NewPassword*

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*旧密码* |一个指定用户现有密码的 **String** 值。如果该用户当前没有密码，则使用空字符串 ("") 作为 *OldPassword*。|
|*新密码* |一个指定新密码的 **String** 值。|

## <a name="remarks"></a>备注

出于安全原因，除了新密码之外还必须指定旧密码。

如果提供程序不支持管理受任者属性，则会发生错误。

