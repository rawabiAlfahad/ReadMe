# ReadMe
## CRUD Asp.net


Select :

```
 CRUD myCrud = new CRUD(); //this is file called CRUD
            String mySql = @"select IdCustmor ,fName , lName , country 
                           from SignUp4 s inner join country c on s.countryId = c.countryId"; // Query
            SqlDataReader dr = myCrud.getDrPassSql(mySql);
            gvsign.DataSource = dr;
            gvsign.DataBind();
```



Insert:

```
 CRUD myCrud = new CRUD();
            string mySql = @"insert SignUp4 (fName,lName,countryId)
                                   values(@fName,@lName,@countryId)";
            Dictionary<string, object> myPara = new Dictionary<string, object>();
            myPara.Add("@fName", txtfName.Text);
            myPara.Add("@lName", txtLastName.Text);
            myPara.Add("@countryId", ddlcountry.SelectedItem.Value);
            int rtn = myCrud.InsertUpdateDelete(mySql, myPara);
                if (rtn >=1)
            { lblOutput.Text = "Operation Successfull !"; }
            else
            { lblOutput.Text = "Operation Failed !"; }

```

Update:

```
 CRUD myCrud = new CRUD();
            String mySql = @"update SignUp4
	        set fName=@fName , lName=@lName , countryId=@countryId
	        where IdCustmor = @IdCustmor";
            Dictionary<string, object> myPara = new Dictionary<string, object>();
            myPara.Add("@IdCustmor", int.Parse(txtid.Text));
            myPara.Add("@fName", txtfName.Text);
            myPara.Add("@lName", txtLastName.Text);
            myPara.Add("@countryId", ddlcountry.SelectedItem.Value);
            int rtn = myCrud.InsertUpdateDelete(mySql, myPara);
            if (rtn >= 1)
            { lblOutput.Text = "Operation Successfull !"; }
            else
            { lblOutput.Text = "Operation Failed !"; }

```

Delete:

```

 CRUD myCrud = new CRUD();
            string mySql = @" delete SignUp4 where IdCustmor=@IdCustmor "; // We used Primary Key
            Dictionary<string, object> myPara = new Dictionary<string, object>();
            myPara.Add("@IdCustmor", int.Parse(txtid.Text));
            int rtn = myCrud.InsertUpdateDelete(mySql, myPara);
            if (rtn >= 1)
            { lblOutput.Text = "Operation Successfull "; }
            else
            { lblOutput.Text = "Operation Failed "; }

```
