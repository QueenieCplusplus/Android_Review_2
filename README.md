# Android_Review_2
Fragment

1. code in MainActivity.kt
 
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
            // create TitleFragment.kt and its related UI layout called fragemt_title
          
          }
        
        }
        
2. Select File->New->Fragment->Fragment (Blank) to create a new Fragment UI layout called fragment_title.xml instead of Activity layout. And add ConstraintLayout uder layer of layout inside it. Beside it, the layout will use navigation modules by default.
 
        <?xml encoding="utf-8"?>
        
        <layout
          xmlns:android=""
          xmlns:app=""
          xmlns:tools=""
          tools:context="com.example.android.katesapp.TitleFragment"
        >
          
          <android.constraintlayout.widget.ConstraintLayout
            android:id="@+id/titleConstraint"
          />
          
        </layout>

3. add <fragment> UI tag in layout called activity_main.xml.
  
       <?xml encoding="utf-8" xmlns:android="" xmlns:app=""?>
       
       <layout>
        <LinearLayout
          android:orientation="vertical"
        >
          <fragment
            android:id="@id/titleFragment"
            android:name="com.example.android.katesapp.TitleFragment"
          />
        </LnearLayout>
       </layout>

4. add Button and ImageView in fragment_title.xml.
  
          <?xml encoding="utf-8"?>
        
          <layout
            xmlns:android=""
            xmlns:app=""
            xmlns:tools=""
            tools:context="com.example.android.katesapp.TitleFragment"
          >
          
            <android.constraintlayout.widget.ConstraintLayout
              android:id="@+id/titleConstraint"
              android:layout_width="match_parent"
              androif:layout_height="match_parent"
              
              <Button/>
              <ImageView/>>
              
            />
          
         </layout>
  

        }
        
5. use DataBindingUtil.inflate to inflate (or return) the titleFragment in onCreateView phase in TitleFragment.kt, code the TitleFragment which is a subclass of the Fragment class.

       package com.example.android.katesapp
       
       [default modules]
       import androidx.fragment.app.Fragment
       import android.os.Bundle
       
       // Mian feature hereby for Fragment
       [databinding modules]
       import androidx.databinding.DataBindingUtil
       import com.example.android.katesapp.databinding.FragmentTitleBinding
       
       [view modules]
       import andorid.view.View
       import android.view.ViewGroup
       
       // Inflater feature
       import android.view.LayoutInflater
       
       class TitleFragment: Fragment(){
       
         override fun onCreateView(inflator: LayoutInfator, container: ViewGroup?, savediInstanceState: Bundle?): View?{
         
           val binding = DataBindingUtil.inflate<FragmentTitleBinding>(inflater, R.layout.fragment_title, container, false)
           
           // means fragment_title.xml layout
           return binding.root
         
         }
      
       }
       
6. create another fragment called InfoFragment.kt, We try not to use databinding this time.

       package com.example.android.katesapp
       
       [default modules]
       import androix.fragment.app.Fragment
       import android.os.Bundle
       
       [inflater feature]
       import android.view.LayoutInflator
       
       [view modules]
       import android.view.View
       import android.view.ViewGroup
       
       class InfoFragment: Fragment(){
       
         override fun onCreateView(inflater: LayoutInflater, container: ViewGroup?, savedInstanceState: Bundle?): View?{
         
           return inflater.inflate(R.layout.fragment_info, container, false)
         
         }
       
       }
   
7. the UI layout for fragement called fragment_info.xml related with code called Info InfoFragment.kt
   And we use ScrollView instead of plain layout style, then a ConstraintLayout inside it.

       <?xml encoding="utf-8"?>
       
       <ScrollView
       
         xmlns:android=""
         xmlns:app=""
         xmlns:tools=""
         tools:context="com.example.android.katesapp.InfoFragment"
       
         <androidx.constraintlayout.widget.ConstrainLayout
            android:layout_width="match_parent"
            androif:layout_height="wrap_content"
         
            <ImageView/>
            
            <TextView/>
         
         />
 
       />


8. set up the properties of UI element examples:

    https://github.com/google-developer-training/android-kotlin-fundamentals-apps/blob/master/AndroidTriviaFragment/app/src/main/res/layout/fragment_about.xml




