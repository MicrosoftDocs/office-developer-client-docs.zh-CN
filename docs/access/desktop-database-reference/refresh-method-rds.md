---
title: Refresh 方法 (RDS)
TOCTitle: Refresh Method (RDS)
ms:assetid: 968baa7c-9128-7155-a1eb-d77aedda6601
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249668(v=office.15)
ms:contentKeyID: 48546450
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bccb7c14b5b8666a5058ad8de489ef248f39ddda
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868628"
---
# <a name="refresh-method-rds"></a>Refresh 方法 (RDS)


**适用于**： Access 2013、 Office 2013

可重新查询在 [Connect](connect-property-rds.md) 属性中指定的数据源并更新查询结果。

## <a name="syntax"></a>语法

*DataControl*。刷新

## <a name="parameters"></a>参数

  - *DataControl*

  - 一个代表 [RDS.DataControl](datacontrol-object-rds.md) 对象的对象变量。

## <a name="remarks"></a>备注

在使用 [Refresh](connect-property-rds.md) 方法之前，必须设置 [Connect](server-property-rds.md)、[Server](https://msdn.microsoft.com/library/jj248989\(v=office.15\)) 和 **SQL** 属性。窗体上与 **RDS.DataControl** 对象关联的所有数据绑定控件都将反映新的记录集，之前存在的任何 [Recordset](recordset-object-ado.md) 对象都被释放，任何未保存的更改都被放弃。 **Refresh** 方法自动使第一条记录成为当前记录。

在处理数据时，最好定期调用 **Refresh** 方法。如果检索数据后将其在客户端计算机上放置一段时间，该数据很可能会过期，而您所做的任何更改都有可能失败，因为其他人可能在您之前更改了记录并提交了更改。

