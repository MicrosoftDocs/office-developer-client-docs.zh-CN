---
title: View 对象 (ADOX-访问桌面数据库引用)
TOCTitle: View Object (ADOX)
ms:assetid: 3b2e9972-8a0d-eaa3-1c93-ae0665a47f02
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249149(v=office.15)
ms:contentKeyID: 48544280
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ca58dd83ee3d3675a4ca272e1074b8d8cc930391
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468816"
---
# <a name="view-object-adox"></a><span data-ttu-id="1df6b-102">View 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="1df6b-102">View Object (ADOX)</span></span>


<span data-ttu-id="1df6b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1df6b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1df6b-p101">表示经过筛选的记录集或虚拟表。与 ADO [Command](command-object-ado.md) 对象一起使用时， **View** 对象可用于添加、删除或修改视图。</span><span class="sxs-lookup"><span data-stu-id="1df6b-p101">Represents a filtered set of records or a virtual table. When used in conjunction with the ADO [Command](command-object-ado.md) object, the **View** object can be used for adding, deleting, or modifying views.</span></span>

## <a name="remarks"></a><span data-ttu-id="1df6b-106">说明</span><span class="sxs-lookup"><span data-stu-id="1df6b-106">Remarks</span></span>

<span data-ttu-id="1df6b-p102">视图是从其他数据库表或视图创建的虚拟表。使用 **View** 对象，无需了解或使用提供程序的"CREATE VIEW"语法，即可创建视图。</span><span class="sxs-lookup"><span data-stu-id="1df6b-p102">A view is a virtual table, created from other database tables or views. The **View** object allows you to create a view without having to know or use the provider's "CREATE VIEW" syntax.</span></span>

<span data-ttu-id="1df6b-109">使用 **View** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1df6b-109">With the properties of a **View** object, you can:</span></span>

  - <span data-ttu-id="1df6b-110">使用 [Name](name-property-adox.md) 属性标识视图。</span><span class="sxs-lookup"><span data-stu-id="1df6b-110">Identify the view with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="1df6b-111">使用 **Command** 属性指定可用于添加、删除或修改视图的 ADO [Command](command-property-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="1df6b-111">Specify the ADO **Command** object that can be used to add, delete, or modify views with the [Command](command-property-adox.md) property.</span></span>

  - <span data-ttu-id="1df6b-112">使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。</span><span class="sxs-lookup"><span data-stu-id="1df6b-112">Return date information with the [DateCreated](datecreated-property-adox.md) and [DateModified](datemodified-property-adox.md) properties.</span></span>

