# Android_Review_2
Fragment


1. add <fragment> UI tag in layout called activity_main.xml.
  
       <?xml encoding="utf-8" xmlns:android="" xmlns:app=""?>
       
       <layout>
        <LinearLayout
          android:orientation="vertical"
        >
          <fragment
            android:id="@id/titleFragment"
            android:name="com.example.android.navigation.TitleFragment"
          />
        </LnearLayout>
       </layout>
  
 
 2. create a new Fragment UI layout called fragment_title.xml instead of Activity layout. And add ConstraintLayout uder layer of layout inside it. Beside it, the layout will use navigation modules by default.
 
        <?xml encoding="utf-8"?>
        
        <layout
          xmlns:android=""
          xmlns:app=""
          xmlns:tools=""
          tools:context="com.example.android.navigation.TitleFragment"
        >
          
          <android.constraintlayout.widget.ConstraintLayout
            android:id="@+id/titleConstraint"
          />
          
        </layout>

  3. add Button and ImageView in fragment_title.xml.
  
          <?xml encoding="utf-8"?>
        
          <layout
            xmlns:android=""
            xmlns:app=""
            xmlns:tools=""
            tools:context="com.example.android.navigation.TitleFragment"
          >
          
            <android.constraintlayout.widget.ConstraintLayout
              android:id="@+id/titleConstraint"
              
              <Button/>
              <ImageView/>>
              
            />
          
         </layout>
  
  
