---
title: View 对象 (ADOX-Access 桌面数据库参考)
TOCTitle: View object (ADOX)
ms:assetid: 3b2e9972-8a0d-eaa3-1c93-ae0665a47f02
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249149(v=office.15)
ms:contentKeyID: 48544280
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b3b5d25a727233b5fda5627df8dff952003bbfe3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306046"
---
# <a name="view-object-adox"></a><span data-ttu-id="effb4-102">View 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="effb4-102">View object (ADOX)</span></span>


<span data-ttu-id="effb4-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="effb4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="effb4-p101">表示经过筛选的记录集或虚拟表。与 ADO [Command](command-object-ado.md) 对象一起使用时，**View** 对象可用于添加、删除或修改视图。</span><span class="sxs-lookup"><span data-stu-id="effb4-p101">Represents a filtered set of records or a virtual table. When used in conjunction with the ADO [Command](command-object-ado.md) object, the **View** object can be used for adding, deleting, or modifying views.</span></span>

## <a name="remarks"></a><span data-ttu-id="effb4-106">注解</span><span class="sxs-lookup"><span data-stu-id="effb4-106">Remarks</span></span>

<span data-ttu-id="effb4-p102">视图是从其他数据库表或视图创建的虚拟表。使用 **View** 对象，无需了解或使用提供程序的“CREATE VIEW”语法，即可创建视图。</span><span class="sxs-lookup"><span data-stu-id="effb4-p102">A view is a virtual table, created from other database tables or views. The **View** object allows you to create a view without having to know or use the provider's "CREATE VIEW" syntax.</span></span>

<span data-ttu-id="effb4-109">使用 **View** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="effb4-109">With the properties of a **View** object, you can:</span></span>

  - <span data-ttu-id="effb4-110">使用 [Name](name-property-adox.md) 属性标识视图。</span><span class="sxs-lookup"><span data-stu-id="effb4-110">Identify the view with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="effb4-111">使用 [Command](command-property-adox.md) 属性指定可用于添加、删除或修改视图的 ADO **Command** 对象。</span><span class="sxs-lookup"><span data-stu-id="effb4-111">Specify the ADO **Command** object that can be used to add, delete, or modify views with the [Command](command-property-adox.md) property.</span></span>

  - <span data-ttu-id="effb4-112">使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。</span><span class="sxs-lookup"><span data-stu-id="effb4-112">Return date information with the [DateCreated](datecreated-property-adox.md) and [DateModified](datemodified-property-adox.md) properties.</span></span>

