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
  
 
 2. Select File->New->Fragment->Fragment (Blank) to create a new Fragment UI layout called fragment_title.xml instead of Activity layout. And add ConstraintLayout uder layer of layout inside it. Beside it, the layout will use navigation modules by default.
 
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
  
 4. code in MainActivity.kt
 
        package com.example.android.katesapp
        
        [default modules]
        import androidx.appcompat.app.AppCompatActivity
        import android.os.Bundle
        
        [add databinding module]
        import androidx.databinding.DtatBindingUtil
        
        [add navigation module]
        import com.example.android.navigation.databinding.ActivityDataBinding
        
        class MainActivity: AppCompatActivity(){
          
          override fun onCreate(saveInstanceState: Bundle?){
          
            super.onCreate(saveInstanceState)
            val binding = DataBindingUtil.setContentView<ActivityMainBinding>(this, R.layout.activity_main)
            
            // TODO:
            // inflate
          
          }
        
        }
        
5. use DataBindingUtil.inflate to inflate (or return) the titleFragment in onCreateView phase in MainActivity.

        package com.example.android.katesapp
        
        [default modules]
        import androidx.appcompat.app.AppCompatActivity
        import android.os.Bundle
        
        [add databinding module]
        import androidx.databinding.DtatBindingUtil
        
        [add navigation module]
        import com.example.android.navigation.databinding.ActivityDataBinding
        
        class MainActivity: AppCompatActivity(){
          
          override fun onCreate(saveInstanceState: Bundle?){
          
            super.onCreate(saveInstanceState)
            val binding = DataBindingUtil.setContentView<ActivityMainBinding>(this, R.layout.activity_main)
            
            // TODO:
            // inflate
            
          
          }
        
        }


