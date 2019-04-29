---
title: 使用信息权限管理设置
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
keywords:
- information rights management [infopath 2007],InfoPath 2007, Information Rights Management,IRM [InfoPath 2007]
localization_priority: Normal
ms.assetid: 4ad91898-b23e-4410-8839-a65259e53d37
description: Microsoft InfoPath 中提供了两种信息权限管理 (IRM) 设置：一种用于保护对 InfoPath 表单模板的访问，另一种用于控制对已填好表单中包含的表单数据的访问和操作。
ms.openlocfilehash: 6f7317cfdc4e6bfc89482e813b1670c8b8861a6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420008"
---
# <a name="work-with-information-rights-management-settings"></a>使用信息权限管理设置

Microsoft InfoPath 中提供了两种信息权限管理 (IRM) 设置：一种用于保护对 InfoPath 表单模板的访问，另一种用于控制对已填好表单中包含的表单数据的访问和操作。
  
> [!NOTE]
> 权限限制只能用于与 InfoPath 编辑器兼容的表单模板。与浏览器兼容的表单模板不支持 IRM。 
  
## <a name="adding-the-manage-credentials-command-to-the-quick-access-toolbar"></a>将"管理凭据"命令添加到快速访问工具栏中

默认情况下，用于处理 IRM 设置的“管理凭据”**** 命令在设计表单模板时不可用。可使用以下步骤将其添加到“快速访问工具栏”**** 中。
  
### <a name="add-the-manage-credentials-command-to-the-quick-access-toolbar"></a>将"管理凭据"命令添加到快速访问工具栏中

1.  单击“快速访问工具栏”**** 右侧的箭头，以打开“自定义快速访问工具栏”**** 菜单，然后单击“更多命令”****。
    
2. 在“从下列位置选择命令”**** 列表中，选择“所有命令”****。
    
3. 将列表向下滚动到“管理凭据”****，然后单击“添加”****。
    
4. Click **OK**.
    
有关使用 InfoPath 中的“管理凭据”**** 命令和“权限”**** 对话框的详细信息，请参阅 InfoPath 帮助中的“创建具有受限权限的表单模板”主题。 
  
## <a name="the-irm-object-model"></a>IRM 对象模型

使用 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.aspx) 类可访问 [UserPermissionCollection](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.aspx) 和可应用于表单的 IRM 权限设置。要访问与表单模板关联的 **Permission** 对象，请使用 [XmlForm](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.Permission.aspx) 类的 [Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.XmlForm.aspx) 属性。返回的 **Permission** 对象提供对与表单模板以及用该模板创建的每个表单实例关联的 [UserPermission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.aspx) 对象集合的访问。 
  
不论权限是否仅限于活动的表单模板， **Permission** 对象及其属性和成员都可用。使用 [Enabled](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.Enabled.aspx) 属性可以确定表单是否具有受限的权限。 
  
通过使用 Permission 类的属性和方法按以下方式之一来启用表单的权限：
  
将 **Enabled** 属性设置为 **true**。
  
设置 [DocumentAuthor](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.DocumentAuthor.aspx) 属性。 
  
设置 [RequestPermissionUrl](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.RequestPermissionUrl.aspx) 属性。 
  
将 [StoreLicenses](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.StoreLicenses.aspx) 属性设置为 **true** 或 **false**。
  
调用 [ApplyPolicy](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.ApplyPolicy.aspx) 方法。 
  
> [!NOTE]
> 如果用户计算机上未安装 Windows 权限管理客户端，则使用 **Permission** 类将引发异常。 
  
要以编程方式使用表单中各个用户的 IRM 设置，请使用 **UserPermissionCollection** 和 **UserPermission** 类。 
  
A **UserPermission** object associates a set of permissions for the current form with a single user and an optional expiration date. Use the [Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Add.aspx) method of the **UserPermissionCollection** class to add and grant a user a set of permissions on the current form. Use the [Remove](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Remove.aspx) method of the **UserPermissionCollection** class to remove a user and the user's permissions. While some permissions granted through the user interface apply to all users, such as printing and expiration date, you can use the **UserPermission** and **UserPermissionCollection** classes to assign them on a per-user basis with per-user expiration dates. The object model allows developers to enumerate permission settings in a form and to provide functionality that allows form users to add permissions to the form without having to use the **Form Permission** task pane or the **Permission** dialog box. 
  
> [!NOTE]
> 在表单处于预览模式时，无法应用权限。因此，在预览表单时， **Permission** 类的所有属性都是只读的。在预览模式下， **Enabled** 属性将始终返回 **false**，如果代码尝试更改此设置，则会引发 **System.Runtime.InteropServices.COMException**，并返回"该属性/方法在预览模式下不可用"错误。同样，当在预览模式下使用时，与 **UserPermission** 和 **UserPermissionCollection** 类关联的方法也将返回此错误消息。 
  
### <a name="overview-of-the-permission-class"></a>Permission 类概述

**UserPermissionCollection** 类提供下列属性和一个方法。 
  
|**名称**|**说明**|
|:-----|:-----|
|[ApplyPolicy](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.ApplyPolicy.aspx) 方法  <br/> |使用策略模板文件将策略应用于表单。  <br/> |
|[DocumentAuthor](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.DocumentAuthor.aspx) 属性  <br/> |获取或设置当前表单作者的电子邮件地址。  <br/> |
|[Enabled](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.Enabled.aspx) 属性  <br/> |获取或设置一个值，指示是否对当前表单启用了 **Permission** 对象所代表的权限设置。  <br/> |
|[PermissionFromPolicy](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.PermissionFromPolicy.aspx) 属性  <br/> |获取或设置一个值，指示是否对当前表单应用了权限策略。  <br/> |
|[PolicyDescription](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.PolicyDescription.aspx) 属性  <br/> |获取应用于当前表单的策略的说明。  <br/> |
|[PolicyName](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.PolicyName.aspx) 属性  <br/> |获取应用于当前表单的策略的名称。  <br/> |
|[RequestPermissionUrl](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.RequestPermissionUrl.aspx) 属性  <br/> |获取或设置供需要当前表单的额外权限的用户联系之用的文件、URL 或电子邮件地址。  <br/> |
|[StoreLicenses](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.StoreLicenses.aspx) 属性  <br/> |获取或设置一个值，指示是否缓存用户查看当前表单的许可，以允许在用户无法连接到权限管理服务器时脱机查看。  <br/> |
|[UserPermissions](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.Permission.UserPermissions.aspx) 属性  <br/> |获取当前表单的 **UserPermissionCollection** 对象。  <br/> |
   
### <a name="overview-of-the-userpermissioncollection-class"></a>UserPermissionCollection 类概述

**UserPermissionCollection** 类提供下列属性和方法。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Add](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Add.aspx) 方法（+3 重载）  <br/> |向当前表单添加一个新用户，可以选择指定权限和到期日期。  <br/> |
|[Remove](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Remove.aspx) 方法  <br/> |从集合中删除具有指定 **UserId** 的 **UserPermission** 对象。  <br/> |
|[RemoveAll](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.RemoveAll.aspx) 方法  <br/> |从集合中删除所有 **UserPermission** 对象。  <br/> |
|[Count](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Count.aspx) 属性  <br/> |获取集合中 **UserPermission** 对象的数目。  <br/> |
|[Item](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermissionCollection.Item.aspx) 属性（+1 重载）  <br/> |获取一个 **UserPermission** 对象。  <br/> |
   
### <a name="overview-of-the-userpermission-class"></a>UserPermission 类概述

**UserPermission** 类提供下列属性和一个方法。 
  
|**名称**|**说明**|
|:-----|:-----|
|[Remove](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.Remove.aspx) 方法  <br/> |从表单的权限中删除当前的 **UserPermission** 对象。  <br/> |
|[ExpirationDate](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.ExpirationDate.aspx) 属性  <br/> |获取或设置当前表单的权限的到期日期（可选），这些权限已分配给与 **UserPermission** 类的实例关联的用户。  <br/> |
|[Permission](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.Permission.aspx) 属性  <br/> |获取或设置代表当前表单的权限的值，这些权限已分配给与 **UserPermission** 类的实例关联的用户。  <br/> |
|[UserId](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.UserPermission.UserId.aspx) 属性  <br/> |获取用户的电子邮件地址，该用户对当前表单的权限由指定的 **UserPermission** 对象确定。  <br/> |
   
### <a name="the-permissiontype-enumeration"></a>PermissionType 枚举

使用 [PermissionType](https://msdn.microsoft.com/library/Microsoft.Office.InfoPath.PermissionType.aspx) 枚举值来设置或读取用户权限。 
  
|**名称**|**说明**|
|:-----|:-----|
|**PermissionType.Change** <br/> |允许用户查看、编辑、复制和保存表单，但不允许打印表单。效果与 **Read**、 **Edit**、 **Save** 和 **Extract** 权限组合相同。  <br/> |
|**PermissionType.Edit** <br/> |允许用户编辑表单。  <br/> |
|**PermissionType.Extract** <br/> |允许具有 **Read** 权限的用户复制表单中的内容。  <br/> |
|**PermissionType.FullControl** <br/> |允许用户添加、更改和删除表单的其他用户的权限。  <br/> |
|**PermissionType.ObjectModel** <br/> |允许用户通过表单文档的对象模型以编程方式访问表单文档。不具有 **ObjectModel** 权限的用户不能使用对象模型来确定他们自己的权限。  <br/> |
|**PermissionType.Print** <br/> |允许用户打印表单。  <br/> |
|**PermissionType.Read** <br/> |允许用户读取（查看）表单。（ **Read** 权限与 **View** 权限等效。）  <br/> |
|**PermissionType.Save** <br/> |允许用户保存表单。  <br/> |
|**PermissionType.View** <br/> |允许用户查看（读取）表单。（ **Read** 权限与 **View** 权限等效。）  <br/> |
   
### <a name="example"></a>示例

在以下示例中，单击“按钮”**** 控件将获取当前表单的 **UserPermissionsCollection**，添加用户并为用户指定“更改”访问级别，以及设置从当前日期向后推算两天的到期日期。 
  
```cs
public void CTRL1_Clicked(object sender, ClickedEventArgs e)
{
   string strExpirationDate = DateTime.Today.AddDays(2).ToString();
   DateTime dtExpirationDate = DateTime.Parse(strExpirationDate);
   this.Permission.UserPermissions.Add("someone@example.com", 
      PermissionType.Change, dtExpirationDate);
}
```

```vb
Public Sub CTRL1_Clicked(ByVal sender As Object, _
   ByVal e As ClickedEventArgs)
   Dim strExpirationDate As String = _
      DateTime.Today.AddDays(2).ToString()
   dtExpirationDate As DateTime = DateTime.Parse(strExpirationDate)
   Me.Permission.UserPermissions.Add("someone@example.com", _
      PermissionType.Change, dtExpirationDate)
End Sub
```


