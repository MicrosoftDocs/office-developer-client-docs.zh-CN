---
title: Procedure 对象 (ADOX)
TOCTitle: Procedure object (ADOX)
ms:assetid: d5fcf0fe-f59f-e114-dc11-515f11c2a2c1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250076(v=office.15)
ms:contentKeyID: 48547972
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 72f0475aeca38b5c6ba6cd2954ff894f00fb6f7f
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922648"
---
# <a name="procedure-object-adox"></a><span data-ttu-id="31929-102">Procedure 对象 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="31929-102">Procedure object (ADOX)</span></span>


<span data-ttu-id="31929-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="31929-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="31929-p101">代表存储过程。与 ADO [Command](command-object-ado.md) 对象一起使用时， **Procedure** 对象可用于添加、删除或修改存储过程。</span><span class="sxs-lookup"><span data-stu-id="31929-p101">Represents a stored procedure. When used in conjunction with the ADO [Command](command-object-ado.md) object, the **Procedure** object can be used for adding, deleting, or modifying stored procedures.</span></span>

## <a name="remarks"></a><span data-ttu-id="31929-106">说明</span><span class="sxs-lookup"><span data-stu-id="31929-106">Remarks</span></span>

<span data-ttu-id="31929-107">使用 **Procedure** 对象，无需了解或使用提供程序的"CREATE PROCEDURE"语法，即可创建存储过程。</span><span class="sxs-lookup"><span data-stu-id="31929-107">The **Procedure** object allows you to create a stored procedure without having to know or use the provider's "CREATE PROCEDURE" syntax.</span></span>

<span data-ttu-id="31929-108">使用 **Procedure** 对象的属性和集合，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="31929-108">With the properties of a **Procedure** object, you can:</span></span>

  - <span data-ttu-id="31929-109">使用 [Name](name-property-adox.md) 属性标识过程。</span><span class="sxs-lookup"><span data-stu-id="31929-109">Identify the procedure with the [Name](name-property-adox.md) property.</span></span>

  - <span data-ttu-id="31929-110">使用 **Command** 属性指定可用于创建或执行过程的 ADO [Command](command-property-adox.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="31929-110">Specify the ADO **Command** object that can be used to create or execute the procedure with the [Command](command-property-adox.md) property.</span></span>

  - <span data-ttu-id="31929-111">使用 [DateCreated](datecreated-property-adox.md) 和 [DateModified](datemodified-property-adox.md) 属性返回日期信息。</span><span class="sxs-lookup"><span data-stu-id="31929-111">Return date information with the [DateCreated](datecreated-property-adox.md) and [DateModified](datemodified-property-adox.md) properties.</span></span>

