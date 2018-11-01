---
title: ChangePassword 方法 (ADOX)
TOCTitle: ChangePassword Method (ADOX)
ms:assetid: 999826a5-3e6b-b6da-b8f6-d61b9a50ceca
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249690(v=office.15)
ms:contentKeyID: 48546519
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 34de673d29d160c715c8e2617d0e2a75e3843904
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25872233"
---
# <a name="changepassword-method-adox"></a>ChangePassword 方法 (ADOX)


**适用于**： Access 2013、 Office 2013



更改用户帐户的密码。

## <a name="syntax"></a>语法

*用户*。ChangePassword*旧密码* *NewPassword*

## <a name="parameters"></a>参数

  - *旧密码*

  - 一个指定用户现有密码的 **String** 值。如果该用户当前没有密码，则使用空字符串 ("") 作为 *OldPassword*。

  - *新密码*

  - 一个指定新密码的 **String** 值。

## <a name="remarks"></a>备注

出于安全原因，除了新密码之外还必须指定旧密码。

如果提供程序不支持管理受任者属性，则会发生错误。

