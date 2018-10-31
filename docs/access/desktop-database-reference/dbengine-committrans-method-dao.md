---
title: DBEngine.CommitTrans Method (DAO)
TOCTitle: CommitTrans Method
ms:assetid: 0c9d345f-13ff-7fe6-789d-fbdb43fa54b8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845171(v=office.15)
ms:contentKeyID: 48543197
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 4cdb0a08cf4336716aa86e878b309822f71287c2
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25861377"
---
# <a name="dbenginecommittrans-method-dao"></a>DBEngine.CommitTrans Method (DAO)


**适用于**： Access 2013 |Office 2013

结束当前的事务并保存更改。

## <a name="syntax"></a>语法

*表达式*。CommitTrans （***选项***）

*表达式*一个代表**DBEngine**对象的变量。

### <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>选项</p></td>
<td><p>可选</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>在 Microsoft Access 工作区中，可以在 <strong>CommitTrans</strong> 中包括 <strong>dbForceOSFlush</strong> 常量。这将强制数据库引擎立即刷新对磁盘执行所有更新，而不是临时缓存更新。如果不使用此选项，在应用程序调用 <strong>CommitTrans</strong> 后，用户可立即取回控制权，并且可关闭计算机，同时不会向磁盘写入数据。尽管使用此选项会影响应用程序的性能，但是，如果将缓存的更新保存到磁盘之前计算机可能会关闭，则使用此选项将非常有帮助。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

事务方法 **BeginTrans**、 **CommitTrans** 和 **Rollback** 可在 **Workspace** 对象定义的会话期间管理事务处理。如果要将会话中的数据库发生的一系列更改视为一个单元，请对 **Workspace** 对象使用这些方法。

通常，如果既要更新两个或更多个表中的记录，又要确保完成（提交）所有表中的更改，或者确保不完成（提交）任何表中的更改（回滚），可使用事务维护数据的完整性。例如，如果将现金从一个帐户转到另一个帐户，可以从一个帐户中减去一个金额，然后将此金额添加到另一个帐户。如果其中任意一个更新失败，那么这两个帐户之间将不再平衡。在更新第一条记录之前，使用 **BeginTrans** 方法，然后，如果任何后续更新失败，可以使用 **Rollback** 方法撤消所有更改。成功更新最后一条记录后，使用 **CommitTrans** 方法。

> [!NOTE]
> [!注释] 在一个 **Workspace** 对象中，事务对 **Workspace** 始终是全局的，不会只限于一个 **Connection** 或 **Database** 对象。如果在 **Workspace** 事务中对多个连接或数据库执行操作，解析事务（即使用 **CommitTrans** 或 **Rollback** 方法）将影响对该工作区中所有连接和数据库执行的所有操作。

使用 **CommitTrans** 后，除非事务嵌套在另一个自己回滚的事务中，否则您无法撤消该事务期间所做的更改。如果要嵌套事务，必须先解析当前事务，然后才可以解析更高嵌套级别的事务。

如果要实现具有重叠、非嵌套范围的同步事务，可创建额外的 **Workspace** 对象以包含并发事务。

如果关闭了一个 **Workspace** 对象且没有解析任何待定事务，事务将自动回滚。

如果在没有首先使用 **BeginTrans** 方法的情况下使用了 **CommitTrans** 或 **Rollback** 方法，则会发生错误。

Microsoft Access 工作区中使用的某些 ISAM 数据库可能不支持事务，在这种情况下， **Database** 对象或 **Recordset** 对象的 **Transactions** 属性为 **False**。若要确保数据库支持事务，请在使用 **BeginTrans** 方法之前，检查 **Database** 对象的 **Transactions** 属性的值。如果使用的是基于多个数据库的 **Recordset** 对象，请检查 **Recordset** 对象的 **Transactions** 属性。如果 **Recordset** 完全基于 Microsoft Access 数据库引擎表，则始终都可以使用事务。但是，基于由其他数据库产品创建的表的 **Recordset** 对象可能不支持事务。例如，不能在基于 Paradox 表的 **Recordset** 中使用事务。在这种情况下， **Transactions** 属性为 **False**。如果 **Database** 或 **Recordset** 不支持事务，将忽略这些方法，并且不发生错误。

如果通过 Microsoft Access 数据库引擎访问 ODBC 数据源，则无法嵌套事务。

在 ODBC 工作区中，如果使用 **CommitTrans**，游标可能不再有效。使用 **Requery** 方法查看 **Recordset** 中的更改，或关闭再重新打开 **Recordset**。


> [!NOTE]
> - 可以经常通过中断需要对磁盘中的事务块进行访问的操作，来改善应用程序的性能。这将会缓冲您的操作，并可显著地减少访问磁盘的次数。
> - 在 Microsoft Access 工作区中，事务将记录在一个文件内，该文件保存在由工作站上的 TEMP 环境变量指定的目录中。如果事务日志文件耗尽了 TEMP 驱动器上的可用存储，数据库引擎将触发一个运行时错误。此时，如果使用 **CommitTrans**，将提交不确定的操作次数，但是余下的未完成操作将会丢失，并且必须要重新启动操作。使用 **Rollback** 方法将释放事务日志，同时回滚事务中的所有操作。
> - 在待定事务中关闭克隆 **Recordset** 将导致隐式 **Rollback** 操作。


